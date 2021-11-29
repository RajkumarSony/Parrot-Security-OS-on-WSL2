## Parrot-Security-OS-on-WSL2
Install Parrot-Security-OS terminal on WSL2 (Windows 11)

   # Install WSL
    Open PowerShell as Admin and run:
    >> dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

   # Update to WSL 2
    Open PowerShell as Admin
    >> wsl --set-default-version 2

   # Install GNUPG:
    $ sudo apt install gnupg

   # Debian → Parrot :parrot:
    Let’s get to the fun stuff!
    In your CLI, copy and paste to get the parrot-install.sh 281
    Alternatively, copy the raw text if you don’t trust me :sob:

    $ sudo apt update
    $ sudo apt upgrade -y

    $ chmod a+x parrot-install.sh
    $ sudo ./parrot-install.sh

   # To Upgrade
    $ sudo su
    $ parrot-upgrade
    
   # LAN XRDP Server
      This will create an access port on your Local Area Network through the WSL network adapter.
      Allows you to connect to an operating system.
      Note: You can only remote into a single WSL machine at a time (b/c they share an IP address)

      $ apt-get install xrdp
      I created a bash file (rdp.sh) with

          #!/bin/bash
          /etc/init.d/xrdp start
          ip addr
          
          
