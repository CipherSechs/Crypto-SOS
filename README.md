# Linux OS
## Description
A USB Bootable Image(Ventoy) file that can be also be used in a Window Hyper-V.

## Download
Source: https://mega.nz/folder/xpgCkagT#avNUl7RJFLCYA8hwDAwq9A  
**Link Expires 20230401**

## Verify
GPG: https://github.com/CipherSechs/GPG

## Setup
Save these files in the same directory
 - @ciphersechs_20230301.vtoy
 - @ciphersechs_20230301.vtoy.sig

### Windows
1. Download [GPG4WIN](https://www.gpg4win.org/)
2. Download CipherSechs_PUBLIC.asc and the *.sig file from [here](https://github.com/CipherSechs/GPG)  
3. Run Kleopatra, click on IMPORT.
4. Select the **CipherSechs_PUBLIC.asc** file
5. Find the **@ciphersechs_20230301.vtoy.sig** file and double click on it.
   "Operation 1: Verifying: '@ciphersechs_20230301.vtoy' with '@ciphersechs_20230301.vtoy.sig'..." will show up
   This process will take a couple of minutes
6. When the operation has finished.  Click on "Show Audit Log"
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
