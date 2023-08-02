# Crypto-SOS
## A full Linux OS install that runs off a 16GB Thumb Drive
A useful and _portable_ Crypto SOS system where it is a known _clean_ device that works on existing computer hardware you own.<br>
Some people recommend having a dedicated system when transacting or dealing with anything crypto related.  I thought there must be a much cheaper and readily available solution(using tried and tested FOSS components) than buying outright hardware just to have a _clean_ operating environment.<br><br>
This is a self-contained *.vtoy([VENTOY](https://www.ventoy.net/en/index.html)) file which has a distro named [Bunsenlabs](https://www.bunsenlabs.org/)(based on Debian 11)that can be also be used in a Window Hyper-V.<br><br>
This is an operating system based on Debian 11 which I personally use.  It's essentially what I use when I need to use an OS<br>
that won't be as susceptible to malware/viruses like Windows can be.  I use it mainly to transact crypto with.<br>
AppImages are used where available as it's more user-friendly to non Linux enthusiasts and is also easier to update(just download the latest Appimage, rename and replace in /bin folder).

* The OS contains the usual office and file programs that other Linux OS's have.<br>
* LibreWriter, LibreCalc, GIMP, Inkscape are installed.  Flameshot gui installed for window screenshots/clipping.<br>
* ClamAV(Antivirus for Linux) is installed, along with the ClamTK GUI to interact with.<br>
* VokoscreenNG screen recorder; useful to record transactions.<br>
* Shotcut video editor installed.(AppImage)<br>
* It also has Feather wallet(monero) installed, and Trezor Suite and Ledger Live; both as AppImages.<br>
* It also has KeePassXC the highly recommended FOSS password manager; also as an Appimage.<br>
* KeePassXC is also sandboxed via Firejail so there is no network traffic.<br>
* Default DNS is set as [Quad9](https://www.quad9.net/) for security and privacy.<br>
* Chrome, FireFox, Brave and LibreWolf are installed for browser isolation.<br>
* Decentraleyes, Malwarebytes Browser Guard, Privacy Badger and uBlock Origin browser extensions are all installed on them also.<br>
* TrueCrypt, VeraCrypt, ZuluCrypt and GngPG are also installed for encryption.<br>
* The Linux OS is password protected with LUKS encryption on bootup(password can be changed to suit).<br>
* Virtual Machine Manager(Virt-manager) is already installed, as is DOSBOX and MAME emulator.<br>
* Seahorse and Yubico Authenticator(FIDO2/MFA) are installed too.
* IPFS Desktop installed.(AppImage)
* REALTIME prices of Cryptocurrencies..<br>
  #### There is an editable "WATCH ADDRESSESS" section where you can enter your BTC or LTC address
  ##### BNB, ETH, SHIB, HEX, other addresses can also be added with some extra coding and APIs

![PHOTO](https://github.com/CipherSechs/Crypto-SOS/blob/main/CSOS%20Prices.png)

  ### RSS Feeds from Decrypt and Cryptopanic news aggregators for up to the minute CryptoNews.

![PHOTO](https://github.com/CipherSechs/Crypto-SOS/blob/main/CSOS%20RSS.png)

* Editable NOTES section that stays on the desktop(similar to BGINFO application on Windows machines)

* **Very low overhead of system resources**<br>
## Photo below shows system with 5GB RAM usage, running off a 16GB thumb drive
![PHOTO](https://github.com/CipherSechs/Crypto-SOS/blob/main/CSOS%20Apps01.png)


### Download Link - UEFI systems
https://mega.nz/folder/9XlBUA7Q#lQAg5-orpRjKmRTdZiSJAw<br>
Contains:<br>
   CipherSechs.vtoy      (_UEFI_ bootable, copy this Ventoy file to your USB drive)<br>
   CipherSechs.vtoy.sig  (verify this file using GPG)<br>

### Verify
https://github.com/CipherSechs/GPG

### Checksums
MD2:    424ece18c581703d9a0fb5a94c0dc305<br><br>
MD5:    6558797a06948a9a362317fe05870a77<br><br>
SHA1:   c4bd9c3cdc47454f710a3ecec3377980ab5f9099<br><br>
SHA256: d34cea92d768fd803799f11277b00ce706c142387dbfbeb4bc8bd124294f1cff<br><br>
SHA512: dd4bb99652c0966e65ba48195becc00ee7d32f19f11c36b63cfc393c1ee9ee4837a717312c5f4382c20bfc88d9074e8fceca4fe659ffe228bd8e4ea41ef77f20<br><br>
_(GtkHash to verify the above, use it if you are not sure how to use GPG)_
![PHOTO](https://github.com/CipherSechs/Crypto-SOS/blob/main/CipherSechs%20HASH.png)

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
