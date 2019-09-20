# Brief Linux Server Documentation

### What is the server
The server is just a GUI-less computer that allows network traffic to access its contents



### Basic usage
#### Login
Each user has a username and a password. When entering the password, nothing shows on the screen for security.

#### Remote Login
From any computer in the classroom, you can remote login to the server. First, connect to the local network, NETGEAR65. Network login details are on the router. Open the command line (or PowerShell on the class leptops) and type in:
#### ssh yourusername@192.168.1.222
This will prompt you to type 'yes', then your password.
If done right, you will see the same screen as you would if you logged in directly to the server.

#### Remote File Transfer
Instead of logging in, you can copy files from a local directory on your computer to a directory on the server using 'scp'.

#### scp relative_local_file_path yourusername@192.168.1.222:server_dir_path

If copying a folder,

#### scp -R relative_dir_path yourusername@192.168.1.222:server_dir_path

ex) scp C:\Users\jbrow\OneDrive\Desktop\linux.md joey@192.168.1.222:/home/joey/md  
ex) scp -R C:\Users\jbrow\OneDrive\Desktop joey@192.168.1.222:/home/joey

#### While working in the server...
There are a useful commands that you will use often:

| Command      | Description                                              |
|--------------|----------------------------------------------------------|
| pwd          | shows present working directory (where you are)          |
| cd dir       | enter directory with path dir                            |
| ls           | shows all directories and files in your pwd              |
| mkdir dir    | makes directory with name dir in your pwd                |
| vi file.type | makes file 'file' with type 'type' and enters vi to edit |
| :wq          | save and exit vi when in normal mode                     |
| Esc          | Enter normal mode in vi                                  |
| i            | Enter INSERT mode in vi while in normal mode             |
| vimtutor     | show a bit more info on how to use vi and vim            |
| Ctrl + C     | Exit a process                                           |


### Server Management
#### Updating and Upgrading offline
There are a few ways to do this, one easy way being Keryx.
Follow these links for more information on this:
<https://askubuntu.com/questions/711890/installing-packages-from-usb-to-ubuntu-server-14-04>  
<https://askubuntu.com/questions/974/how-can-i-install-software-or-packages-without-internet-offline?noredirect=1&lq=1>  
<https://launchpad.net/keryxproject>  
<https://askubuntu.com/questions/86358/how-to-obtain-installed-package-files>  
<https://packages.ubuntu.com/bionic/>  

#### APT
APT, or the Advanced Package Tool, managed the updates, upgrades, and installations to the OS
Commands like 'sudo apt update pkg_name', 'sudo apt upgrade pkg_name', and 'sudo apt full-upgrade' are common.

The apt finds where to get deb files from the file /etc/apt/sources/list. This is modified when upgrading offline.

### Linux based laptops
Using the old laptops, I've been able to wipe Win7 and install a linux distro. Only a few laptops had UEFI Boot enabled, but Legacy boot is still an option for the others if you can get it to work.  
Three of the laptops have Ubuntu Desktop 18.04 installed with the Gnome desktop environment disabled. The other laptop has ArchLinux which Brian knows more about.  
If more laptops get Ubuntu Desktop in the future, the installation DvD is in a makeshift envelope labled 'Ubuntu DvD'. This only works on EFI enabled systems.
When Ubuntu Desktop is installed, run the command 'systemctl set-default multi-user.target' to disable GDM (Gnome Display Manager) on boot. This will force the system to boot into terminal.