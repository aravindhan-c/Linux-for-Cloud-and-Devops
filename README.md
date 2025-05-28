# Linux-for-Cloud-and-Devops
DevOps & cloud engineers uses linux commands to move files, Check logs, install softwares, run scripts & troubleshoot issues on daily basis.

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
* nslookup - obtain information for DNS server (Name Server Lookup) (nslookup <domain name>)
* ssh-keygen - generate a public/private key pair (ssh-keygen -t rsa)
* apt-get - manage packages in linux
* man - give details about the command (man touch)
* nproc - cpu details (no. of processors)
* tree - display directory in tree structure
* ln - create symbolic links

## File system commands:
* mkdir - make directory (mkdir abc - single directory, mkdir abc def geh - multiple directories)
* mkdir -p /abc/def/ghi - create directory path (dirctories inside directories)
* mkdir abc(1..3} - creat a series of numbered directories (abc1 abc2 abc3)
* rmdir - remove an empty directory
* touch - create an empty file (touch file.txt)
* echo - create a file with some content (echo "hello" >> file.txt) (overwrites if file already exist)
* cat - create and writes to a file (cat > file.txt) (type content and ctrl+D to save)
* nano - opens a terminal text editor (nano file.txt) (ctrl+x to exit and save)
* vi or vim - opens powerful terminal text editor (vi file.txt) (press i to insert mode, esc to exit, :wq! to save)
* more/less - view files page by page

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
* id - display user and group information

## Group Management
* sudo groupadd <grpname> - creating a new group
* sudo groupdel <grpname> - deletig a group
* sudo usermod -g <groupname> <username> - adding a user to a group

## Process management
* ps aux - display all currently running processes (process status)
* top - real-time info about currently running processes of the system
* kill <pid> - terminate a process
* systemctl - manage system services
* du - display directory disk space usage 
* df -h - display disk space usage
* free - display free & used memory details of the system
* free -g - display memory details in GB
* uptime - display system uptime
* nice - set process priority

## Networking
* ifconfig - information about network interface/ display network configuration
* ip - view and manage network settings. replacemet of ifconfig.(ip addr show)
* netstat - network statistics
* ss - socket statistics
* ping - test network connectivity
* traceroute - trace the route packets take to a network host
* telnet - connect to remote host
* ssh - securely connect to remote servers
* scp - securely copy files between hosts
* curl - retrives information from the internet and display (curl url)
* curl -o - saves the data into a file on the local (curl -o sample.txt url)
* wget - download the files from internet

## File System Permissions
Three types of permission - read, write & execute. Permissions can be attached to user(u), group(g) & other(o)
* ls -ld - list permissions of the directory
* d rwx rwx rwx - d(file type) rwx(for user) rwx(group) rwx(others)
* 0 or --- - no permission; 1 or --x - execute; 2 or -w- - write; 4 or r-- - read
* chmod - change permission of file and directory (chmod <permission of user group other> {filename})
* chown - change the owner of the file and directory (chown <ownername> <filename>)
* chgrp - change the group ownership of the files
* cat - read and concatenate the text inside the files (cat -b <filename> - add line numbers while displaying contnent on terminal; cat -e <filename> - add $ symbol at the end of each line of the file)
* grep - global regular expression print - searches files for a particular pattern and displays all the lines that contains the pattern (grep <flag or search_word> filename)
* grep -i - Delivers results for case-insensitive strings
* grep -n - retrives the corresponding string and their respective line numbers
* grep - v - provides the output of the lines that do not contain the search string
* sort - print the output of the file in specified order (sort filename)
* head - display the first few lines of one or more text files (head -n 2 filename)
* tail - display the last few files of one or more text files (tail -n 2 filename)
* find - search files and directories based on criteria like name, size, type and date (find . -name "filename"
* sed - stream line editor - text manipulation
* wc - word count

## Logs and troubleshooting
* journalctl - view system logs
* tail/grep - log files for troubleshooting
* dmesg - display kernel message
* strace - trace system calls and signals
* lsof - list open files and processes
* nc - netcat - network utility for read/writing to network connections
* tcpdump - network packet analyzer

## Package management
* yum/def - package mgmt for RHEL-based systems
* rpm - package mgmt tool for RPM packages
* yum list/dnf list - list installed packages
* yum install/dnf install - install packaes
* yum remove/dnf remove - remove packages
* yum update/dnf update - update packages
* yum search/dnf search - search package repositories

## Monitoring and Resource Usage
* iotop: Monitor I/O usage by processes.
* atop: Advanced system performance monitor.
* vmstat: Virtual Memory Statistics.
* sar: System activity report.
* nmon: Performance monitoring tool.
* iftop: Network bandwidth monitoring.

## Miscellaneous commands
* trap - trapping signals (trap "echo don't use ctrl+c" SIGINGT)
* awk - text processing and pattern matching - retive info in specific column (ps -ef | grep dog | awk -F " " "{print $4}")

## Linux File System Hierarchy 
Defines directory structure and directory contents managed by linux foundations. The root directory / is the starting point for the entire Linux filesystem hierarchical tree. It is the top-most directory from which all other file systems are mounted at system boot up. All files and folders will branch from the root directory even if the data is stored in different places physically.

The root directory is owned by the root user (admin) and its permissions are tightly controlled to allow only administrators to add, remove, or modify files and folders in this directory.

#SUB-DIRECTORY PURPOSE
/bin      common binary executables used by all users | essential user command binaries like ls, cp, rm; needed in single-user mode
/boot     files associated with boot loader  |  boot loader files including the kernel, initrd, and GRUB configuration
/dev      attached devices (usb, cdrom, mouse, keyboard) | device files representing hardware (USB, disks, terminals); managed by udev
/etc      configuration files | system-wide configuration files and scripts (e.g., passwd, fstab, sshd_config)
/home     personal directories for each user account | user-specific directories storing personal files and settings (e.g., /home/user)
/lib      shared system libraries | shared libraries (.so files) required by binaries in /bin and /sbin
/media    directory for mounting removable devices (floppy drive, cdrom) |  mount point for removable media automatically handled (e.g., USB, CD-ROM)
/mnt      directory for mounting filesystems (nfs, smb) | temporary mount point used by administrators to manually mount filesystems
/opt      optional vendor add-on software | optional third-party application software (e.g., /opt/google/chrome)
/proc     virtual filesystem for system processes/resources information |  virtual filesystem with runtime system/process information (e.g., cpuinfo, meminfo)
/root     home directory for administrator account | home directory of the root user (administrator); separate from /home
/run      storage for runtime information | transient runtime data (e.g., PID files, sockets) since last boot
/sbin     binary executables used by administrator | system administration binaries (e.g., reboot, fdisk, ifconfig); typically used by root
/srv      data for server services | data for services like web or FTP (e.g., /srv/www for web content)
/sys      virtual filesystem for hardware/driver information | virtual filesystem showing kernel devices and drivers (hardware-level info)
/tmp      temporary files purged on reboot | temporary files used by apps; deleted on reboot
/usr      utilities and read-only user data/programs | user utilities, applications, and read-only data (e.g., /usr/bin, /usr/share)
/var      variable and log files | variable data like logs, mail, spool, cache that frequently changes (e.g., /var/log)

Tasks:
1. List all files (including hidden ones) in your home directory and sort them by modification time.
