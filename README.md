# Linux-for-Cloud-and-Devops
DevOps & cloud engineers uses linux commands for move files, Check logs, install softwares, run scripts & troubleshoot issues on daily basis.

File System:
In Linux, everything is represented as a file, including a hardware program. The files are stored in a directory, and every directory contains a file with a tree structure.
The root directory is represented with / (forward slash). It is a top-level directory in Linux.

## Basic Commands:
* pwd - present working directory
* ls - list files and directories
* ls -l - list files and directores with permissions, timestamp and more details
* ls -a - list hidden files and directories
* uanme - print system information 
* unamne -r - print kernel release information
* cd - change directory
* clear - clear terminal screen
* whoami - display current user
* history - history of commands previously executed in current terminal
* free - display free & used memory details of the system
* free -g - display memory details in GB
* nslookup - obtain information for DNS server (Name Server Lookup) (nslookup <domain name>)
* ssh-keygen - generate a public/private key pair (ssh-keygen -t rsa)
* curl - retrives information from the internet and display (curl url)
* wget - download the files from internet
* curl -o - saves the data into a file on the local (curl -o sample.txt url)
* apt-get - manage packages in linux
* du - disk usage space
* df -h - available disk space
* ifconfig - information about network interface
* ip - view and manage network settings. replacemet of ifconfig.(ip addr show)
* man - give details about the command (man touch)
* nproc - cpu details (no. of processors)

## File system commands:
* mkdir - make directory (mkdir abc - single directory, mkdir abc def geh - multiple directories)
* mkdir -p /abc/def/ghi - create directory path (dirctories inside directories)
* mkdir abc(1..3} - creat a series of numbered directories (abc1 abc2 abc3)
* touch - create an empty file (touch file.txt)
* echo - create a file with some content (echo "hello" >> file.txt) (overwrites if file already exist)
* cat - create and writes to a file (cat > file.txt) (type content and ctrl+D to save)
* nano - opens a terminal text editor (nano file.txt) (ctrl+x to exit and save)
* vi or vim - opens powerful terminal text editor (vi file.txt) (press i to insert mode, esc to exit, :wq! to save)

### Copy and pasting files and directories (cp, rm)
* cp -rvf abc1 abc - copy files with verbose and force(overwrite if necessary)
* rm -rvf abc - remove directory and its contents

### Renaming files and directories (mv)
* mv abc abc-devops - renaming a directory

## User Management
* sudo useradd <username> - creating a new user
* sudo passwd <username> - setting a password
* sudo userdel <username> - deleting a user
* sudo su <username> - switch to another user
* sudo su - - switch to root user
* sudo usermod -l <newname> <oldname> - renaming a user

## Group Management
* sudo groupadd <grpname> - creating a new group
* sudo groupdel <grpname> - deletig a group
* sudo usermod -g <groupname> <username> - adding a user to a group

## Process management
* ps aux - display all currently running processes (process status)
* top - real-time info about currently running processes of the system
* kill <pid> - terminate a process

## File System Permissions
Three types of permission - read, write & execute. Permissions can be attached to user(u), group(g) & other(o)
* ls -ld - list permissions of the directory
* d rwx rwx rwx - d(file type) rwx(for user) rwx(group) rwx(others)
* 0 or --- - no permission; 1 or --x - execute; 2 or -w- - write; 4 or r-- - read
* chmod - change permission of file and directory (chmod <permission of user group other> {filename})
* chown - change the owner of the file and directory (chown <ownername> <filename>)
* cat - read and concatenate the text inside the files (cat -b <filename> - add line numbers while displaying contnent on terminal; cat -e <filename> - add $ symbol at the end of each line of the file)
* grep - global regular expression print - searches files for a particular pattern and displays all the lines that contains the pattern (grep <flag or search_word> filename)
* grep -i - Delivers results for case-insensitive strings
* grep -n - retrives the corresponding string and their respective line numbers
* grep - v - provides the output of the lines that do not contain the search string
* sort - print the output of the file in specified order (sort filename)
* head - display the first few lines of one or more text files (head -n 2 filename)
* tail - display the last few files of one or more text files (tail -n 2 filename)
* find - search files and directories based on criteria like name, size, type and date (find . -name "filename"

## Miscellaneous commands
* trap - trapping signals (trap "echo don't use ctrl+c" SIGINGT)
* awk - retive info in specific column (ps -ef | grep dog | awk -F " " "{print $4}")
