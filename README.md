# Linux OS
## Description
A USB Bootable Image(Ventoy) file that can be also be used in a Window Hyper-V.

### Download Link
Source: https://mega.nz/folder/xpgCkagT#avNUl7RJFLCYA8hwDAwq9A  
**Link Expires 20230401**

### Verify
GPG: https://github.com/CipherSechs/GPG

### Saving
Save these files in the same directory
 - @ciphersechs_20230301.vtoy
 - @ciphersechs_20230301.vtoy.sig

### Windows
1. Download [GPG4WIN](https://www.gpg4win.org/)
2. Download **CipherSechs_PUBLIC.asc** and the .sig file from [here](https://github.com/CipherSechs/GPG)  
3. Run Kleopatra, click on IMPORT.
4. Select the **CipherSechs_PUBLIC.asc** file
5. Find the **@ciphersechs_20230301.vtoy.sig** file and double click on it.  
   "Operation 1: Verifying: '@ciphersechs_20230301.vtoy' with '@ciphersechs_20230301.vtoy.sig'..." will show up  
   This process will take a couple of minutes.
6. When the operation has finished, click on "Show Audit Log".
7. The results should report "**Good signature from "CipherSechs (Linux) <ciphersechs@ciphersechs.com>**"  

```
gpg: Signature made 2023-03-02 16:42:46 W. Australia Standard Time
gpg:                using RSA key 3847AEA443DFDA8CFE3F90C82366A97FC53A18EC
gpg: Good signature from "CipherSechs (Linux) <ciphersechs@ciphersechs.com>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
Primary key fingerprint: 3847 AEA4 43DF DA8C FE3F  90C8 2366 A97F C53A 18EC
```

### Linux
1. Install GPG on your Linux system
  - Debian/Ubuntu: **sudo apt-get install gnupg**
  - Fedora/RHEL/CentOS: **sudo dnf install gnupg**
  - Arch Linux: **sudo pacman -S gnupg**
2. Import the **CipherSechs_PUBLIC.asc** signed key file  
    **gpg --import CipherSechs_PUBLIC.asc**  
3. Verify that the CipherSechs_PUBLIC.asc key has been imported  
    **gpg --list-keys**
4. Verify the **@ciphersechs_20230301.vtoy.sig** signature file with the **@ciphersechs_20230301.vtoy** file  
    **gpg --verify @ciphersechs_20230301.vtoy.sig**
5. Confirm that results show "**Good signature from "CipherSechs (Linux) <ciphersechs@ciphersechs.com>**"(as above)


## Installation
1. You'll need to boot into Windows and download and install [Ventoy](https://ventoy.net/en/download.html)
2. Have a USB flash drive(16GB+) that is preferably USB 3.0/3.1/3.2 speed.
3. Run Ventoy2Disk.exe, to install Ventoy on the USB flash drive.  
   In one of the drop down menu's you can choose to partition the USB as exFAT(able to r/w with MacOS) or NTFS.  
  ** **IMPORTANT: You MUST format the drive as NTFS if you require the @ciphersechs_20230301.vtoy file to be compatible with Windows Hyper-V Virtual Machine** **
5. Copy the **@ciphersechs_20230301.vtoy** to the USB drive
6. Go into the command prompt on the USB drive and create a symbolic link  
   **mklink @ciphersechs_20230301.vhd @ciphersechs_20230301.vtoy**  
This creates a 1kb file(symbolic link) that will be identified by Windows Hyper-V as a .VHD file, but points to the .VTOY file.  
*NOTE: You can configure the Ventoy boot settings using VentoyPlugson.exe to change default timeouts, GUI/CLI output, background, etc*

## Usage
### Linux
- Restart your computer, be sure that the USB drive is plugged in.
- Depending on your motherboard BIOS, press one of the function keys to bypass boot priority in BIOS.
  eg. for ASUS motherboards the key is F8.
- Select the USB drive that has the .VTOY file installed on it.  The Linux OS will automatically boot.

### Windows Hyper-V
- Start Windows 'Hyper-V Manager'.
- On the left pane, right click on your PC, click NEW > Virtual Machine.
- Select defaults on the first 3 prompts.  On ASSIGN MEMORY, specify at least 4096MB, click NEXT.
- On CONNECT VIRTUAL HARD DISK, select USE AN EXISTING VIRTUAL HARD DISK.  Locate and select the .VHD file on the USB drive
- Click FINISH.
- On the MIDDLE PANE where it lists Virtual Machines; select the VM you just created, RIGHT CLICK > SETTINGS.
- Go to MEMORY, and change RAM to 4096(minimum), click APPLY.
- Go to PROCESSOR, and change NUMBER OF VIRTUAL PROCESSORS to 3(minimum), click APPLY.
- Scroll down to CHECKPOINTS.  UNCHECK **Enable checkpoints**
*If Enable checkpoints is tick, it won't allow changes on the image to be updated properly*
- Right click on the VM you just created, and click CONNECT.
- Click START, the Linux OS should now start in a Virtual Machine  
*NOTE: You are unable to use the Trezor or Ledger hardware wallets through the VM*
