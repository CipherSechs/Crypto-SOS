# Crypto-SOS
## Description - A full Linux OS install that runs off a 16GB Thumb Drive
This is a self-contained *.vtoy([VENTOY](https://www.ventoy.net/en/index.html)) file which has a distro named [Bunsenlabs](https://www.bunsenlabs.org/)(based on Debian 11)that can be also be used in a Window Hyper-V.<br><br>
This is an operating system based on Debian 11 which I personally use.  It's essentially what I use when I need to use an OS<br>
that won't be as susceptible to malware/viruses like Windows can be.  I use it mainly to transact crypto with.

* The OS contains the usual office and file programs that other Linux OS's have.<br>
* LibreWriter, LibreCalc, GIMP, Inkscape are installed.  Flameshot gui installed for window screenshots/clipping<br>
* It also has Feather wallet(monero) installed, and Trezor Suite and Ledger Live; both as AppImages.<br>
* It also has KeePassXC the highly recommended FOSS password manager; also as an Appimage.<br>
* KeePassXC is also sandboxed via Firejail so there is no network traffic.<br>
* Default DNS is set as [Quad9](https://www.quad9.net/) for security and privacy.<br>
* Chrome, FireFox, Brave and LibreWolf are installed for browser isolation.<br>
* Decentraleyes, Malwarebytes Browser Guard, Privacy Badger and uBlock Origin browser extensions are all installed on them also.<br>
* TrueCrypt, VeraCrypt, ZuluCrypt and GngPG are also installed for encryption.<br>
* The Linux OS is password protected with LUKS encryption on bootup(password can be changed to suit).<br>
* Virtual Machine Manager(Virt-manager) is already installed, as is DOSBOX and MAME emulator.<br>
* Seahorse and Yubico Authenticator(FIDO2/MFA) is also installed too.
* IPFS Desktop installed(AppImage)
* REALTIME prices of Cryptocurrencies

![PHOTO](https://github.com/CipherSechs/Crypto-SOS/blob/main/CSOS%20Prices.png)

* RSS Feeds from Decrypt and Cryptopanic news aggregators for up to date CryptoNews.

![PHOTO](https://github.com/CipherSechs/Crypto-SOS/blob/main/CSOS%20RSS.png)

* Editable NOTES section that stays on the desktop(similar to BGINFO application on Windows machines)

### Download Link
Source: https://mega.nz/file/VfRQUb7K#3hGxmu4l6l54tEE3cGPyY5qYRrNetLSR8l1OyfxQrmY

### Verify
https://github.com/CipherSechs/GPG

### Checksums
MD2:    1678783319f9ed0834c0967d5795b806<br><br>
MD5:    ee975db0335b3fe23958854cc885e899<br><br>
SHA1:   9530e0038477eeda7b32c0012660c3b22e2492ab<br><br>
SHA256: 22e1602d75628e354892680a33d65929842d8dcbb3b71669280aa0e4e9bd056<br><br>
SHA512: 5592709a92882f457a20242e4879eed8b11b5f1b2a41146849f03d08bc46cc5e3a30dafcfd57ffdcea5bd1c9edf6297693a305a784f48b6550f4b90f5daf8018<br><br>
_(GtkHash to verify the above, use it if you are not sure how to use GPG)_


### Saving
Save these files in the same directory
 - CipherSechs.vtoy
 - CipherSechs.vtoy.sig

### Windows
1. Download [GPG4WIN](https://www.gpg4win.org/)
2. Download **CipherSechs_PUBLIC.asc** and the .sig file from [here](https://github.com/CipherSechs/GPG)  
3. Run Kleopatra, click on IMPORT.
4. Select the **CipherSechs_PUBLIC.asc** file
5. Find the **CipherSechs.vtoy.sig** file and double click on it.  
   "Operation 1: Verifying: 'CipherSechs.vtoy' with 'CipherSechs.vtoy.sig'..." will show up  
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
4. Verify the **CipherSechs.vtoy.sig** signature file with the **CipherSechs.vtoy** file  
    **gpg --verify CipherSechs.vtoy.sig**
5. Confirm that results show "**Good signature from "CipherSechs (Linux) <ciphersechs@ciphersechs.com>**"(as above)


## Installation
1. You'll need to boot into Windows and download and install [Ventoy](https://ventoy.net/en/download.html)
2. Have a USB flash drive(16GB+) that is preferably USB 3.0/3.1/3.2 speed.
3. Run Ventoy2Disk.exe, to install Ventoy on the USB flash drive.  
   In one of the drop down menu's you can choose to partition the USB as exFAT(able to r/w with MacOS) or NTFS.  
  ** **IMPORTANT: You MUST format the drive as NTFS if you require the CipherSechs.vtoy file to be compatible with Windows Hyper-V Virtual Machine** **
5. Copy the **CipherSechs.vtoy** to the USB drive
6. Go into the command prompt on the USB drive and create a symbolic link  
   **mklink CipherSechs.vhd CipherSechs.vtoy**  
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
