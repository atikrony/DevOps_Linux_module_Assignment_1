

## 1. File and Directory Operations

### Screenshot:
![File and Directory Operations](/AssignmentLinux/filedirectoryoperations.png)

### Commands with Explanation:

#### Step 1: Navigate to the home directory
```bash
cd home
```
This command moves the current working directory to the `home` directory.

#### Step 2: Create a new directory named 'linux_fundamentals'
```bash
sudo mkdir linux_fundamentals
```
The `mkdir` command creates a new directory named `linux_fundamentals`. The `sudo` prefix ensures necessary permissions.

#### Step 3: Navigate to the new directory
```bash
cd linux_fundamentals
```
Switches to the `linux_fundamentals` directory.

#### Step 4: Create a subdirectory named 'scripts'
```bash
sudo mkdir scripts
```
Creates a subdirectory named `scripts` inside the `linux_fundamentals` directory.

#### Step 5: Create a file named 'example.txt'
```bash
sudo touch example.txt
```
The `touch` command creates a new file named `example.txt`. The `sudo` prefix ensures permission for file creation.

#### Step 6: Copy the file to the 'scripts' directory
```bash
sudo cp example.txt /home/linux_fundamentals/scripts
```
Copies `example.txt` to the `scripts` subdirectory.

#### Step 7: List files in the 'linux_fundamentals' directory
```bash
ls
```
Displays the list of files and directories in `linux_fundamentals`.

#### Step 8: Create a backup directory
```bash
sudo mkdir backup
```
Creates a directory named `backup` inside `linux_fundamentals`.

#### Step 9: Move the file to the backup directory
```bash
sudo mv example.txt /home/linux_fundamentals/backup
```
Moves `example.txt` to the `backup` directory.

#### Step 10: Change permissions of the file
```bash
sudo chmod 644 example.txt
```
Sets file permissions to allow read and write for the owner, and read-only for group and others.

#### Step 11: Verify file permissions in the backup directory
```bash
cd backup
ls -l
```
Navigates to the `backup` directory and lists files with their permissions.

---

## 2. File Ownership and Links

### Screenshot:
![Hard and Soft Links](/AssignmentLinux/Fileodification.png)

### Commands with Explanation:

#### Step 1: Create a new file and list its attributes
```bash
touch original_file.txt
ls -li original_file.txt
```
Creates a file named `original_file.txt` and lists its inode number with permissions.

#### Step 2: Create a hard link
```bash
ln original_file.txt hardlink_file.txt
ls -li
```
Creates a hard link named `hardlink_file.txt` pointing to `original_file.txt`. Both files share the same inode.

#### Step 3: Create a soft (symbolic) link
```bash
ln -s original_file.txt softlink_file.txt
ls -li
```
Creates a symbolic link named `softlink_file.txt` pointing to `original_file.txt`. The symbolic link has its own inode.

#### Step 4: Modify the original file and verify links
```bash
echo "Hello, World!" > original_file.txt
cat hardlink_file.txt
cat softlink_file.txt
```
Any change to `original_file.txt` reflects in `hardlink_file.txt`. The symbolic link references the original content.

---

## 3. User Management Operations

### Screenshot:
![User Management Operations](/AssignmentLinux/useraddmodify.png)

### Commands with Explanation:

#### Step 1: Add a new user named 'student'
```bash
sudo useradd student
```
Creates a new user account named `student`.

#### Step 2: Create a group named 'students'
```bash
sudo groupadd students
```
Creates a group named `students`.

#### Step 3: Add the user 'student' to the 'students' group
```bash
sudo usermod -aG students student
```
Adds the user `student` to the `students` group.

#### Step 4: Create a file and assign ownership
```bash
sudo touch example.txt
sudo chown student:students example.txt
ls -l example.txt
```
Creates a new file named `example.txt`, changes ownership to the user `student` and the group `students`, and displays the updated ownership details.

#### Output:
```plaintext
-rw-r--r-- 1 student students 0 [Date] example.txt
```
Ownership and permissions reflect the updated user and group.

---
```