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

