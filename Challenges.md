1. List all files (including hidden ones) in your home directory and sort them by modification time.
Sol: ls -laht ~
ls → List directory contents
-l → Use a long listing format
-a → Show hidden files (files starting with .)
-h → Display sizes in human-readable format (e.g., KB, MB)
-t → Sort by modification time (newest first)
~ → Home directory
![image](https://github.com/user-attachments/assets/b9752e9e-2c02-449a-ad79-77f2124e102f)

2. Create a directory named devops_challenge_day_1, navigate into it, and create an empty file named day1.txt.
Sol: mkdir devops_challenge_day_1; cd devops_challenge_day_1/; touch day1.txt
![image](https://github.com/user-attachments/assets/cfa5477c-e9ce-400c-838b-b6ab0073cbae)

3. Find the total disk usage of the /var/log directory in human-readable format.
Sol: sudo du -sh /var/log
du → Disk usage command
-s → Summarize total size instead of listing all files
-h → Human-readable format (e.g., KB, MB, GB)
![image](https://github.com/user-attachments/assets/4a209e23-2d76-4d67-8f09-f34e591e0ae4)

4. Create a new user called devops_user and add them to the sudo group.
Sol: sudo useradd devops_user; sudo usermod -aG sudo devops_user; getent group sudo
![image](https://github.com/user-attachments/assets/08adba9a-7dca-47b3-bb3e-d4f06acf6b8c)
![image](https://github.com/user-attachments/assets/5002bbfe-4f72-44cc-a741-e25e7f0c6bf0)

5. Create a group called devops_team and add devops_user to that group.
Sol: sudo groupadd devops_team;  sudo usermod -aG devops_team devops_user; getent group devops_team
 ![image](https://github.com/user-attachments/assets/46590f0b-d298-435e-858b-9b876a413ec7)

6. Change the permissions of day1.txt to allow only the owner to read and write, but no permissions for others.
Sol: sudo chmod 600 day1.txt; ls -l day1.txt
Key points:
First digit: Owner permissions
Second digit: Group permissions
Third digit: Others' permissions
r (4) = Read permission
w (2) = Write permission
x (1) = Execute permission
Sum of values (rwx = 4+2+1 = 7) = All allowed
![image](https://github.com/user-attachments/assets/a51e02a3-722e-4ebc-b4ce-f7d724488de9)

7. Find all files in /etc that were modified in the last 7 days.
Sol:  sudo find /etc -type f -mtime -7
find → Command to search for files and directories.
/etc → The directory to search in.
-type f → Searches for files only (not directories).
-mtime -7 → Finds files modified in the last 7 days (-7 means less than 7 days old).
![image](https://github.com/user-attachments/assets/ce56846e-598b-46df-9097-8f6a11568b76)

8. Write a one-liner command to find the most frequently used command in your shell history.
Sol: history | awk '{count[$2]++} END {for (i in count) print count[i], i}' | sort -nr | head -1
history → Lists the command history.
awk '{count[$2]++;} END {for (i in count) print count[i], i;}'
Extracts and counts occurrences of each command.
sort -nr → Sorts the commands by frequency in descending order.
head -1 → Displays the most frequently used command.
![image](https://github.com/user-attachments/assets/13a04285-2c6b-4c01-8868-f0030fd430e3)

