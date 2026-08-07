# 🚀 Day 4 - Linux Basic Commands & File Management on AWS EC2

## 📚 Topic

- Linux Basic Commands
- Absolute Path vs Relative Path
- File & Directory Management
- Practicing Linux Commands on AWS EC2

---

## 📖 What I Learned

Today, I practiced essential Linux commands on an AWS EC2 instance. I learned how to navigate through directories, create and manage files, and understand the difference between Absolute Path and Relative Path.

I also explored various file management commands used in day-to-day Linux administration.

---

## 📝 Absolute Path vs Relative Path

### 📍 Absolute Path
An **Absolute Path** starts from the **Root (`/`)** directory and specifies the complete location of a file or folder.

**Example:**
```bash
/home/ec2-user/devops/file.txt
```

### 📍 Relative Path
A **Relative Path** starts from the current working directory and does not begin with `/`.

**Example:**
```bash
devops/file.txt
```

---

## 💻 Commands Used

### Check Current Directory

```bash
pwd
```

Displays the current working directory.

---

### Display System Information

```bash
uname
uname -a
```

Shows Linux system information.

---

### List Files & Directories

```bash
ls
ls -l
ls -la
```

- `ls` → Lists files and directories.
- `ls -l` → Displays detailed information.
- `ls -la` → Shows all files, including hidden files.

---

### Create Directory

```bash
mkdir devops
```

Creates a new directory.

---

### Change Directory

```bash
cd devops
cd ..
```

Navigates between directories.

---

### Create Files

```bash
touch file1.txt
touch file2.txt
```

Creates empty files.

---

### Write Content to a File

```bash
cat > file1.txt
```

Creates or overwrites file content.

```bash
cat >> file1.txt
```

Appends content to an existing file.

---

### Display File Content

```bash
cat file1.txt
```

Displays the contents of a file.

---

### Copy Files

```bash
cp file1.txt file2.txt
```

Copies one file to another location.

---

### Move or Rename Files

```bash
mv file1.txt newfile.txt
```

Renames a file.

```bash
mv newfile.txt devops/
```

Moves a file to another directory.

---

### Remove Files

```bash
rm file1.txt
```

Deletes a file.

---

### Remove Directories

```bash
rmdir devops
```

Removes an empty directory.

```bash
rm -r devops
```

Removes a directory and its contents.

---

## 🛠 Practical

- Connected to AWS EC2 using SSH.
- Practiced Linux navigation commands.
- Created directories and files.
- Added and viewed file contents.
- Copied, moved, and renamed files.
- Deleted files and directories.
- Understood Absolute Path and Relative Path.

---

## ✅ Output Screenshots

Successfully practiced Linux basic commands on an AWS EC2 instance and gained hands-on experience in Linux file and directory management.

<img width="1917" height="1072" alt="Screenshot 2026-08-07 111115" src="https://github.com/user-attachments/assets/0d2de637-51ab-4a00-9e58-ffe97bfe0d8e" />
<img width="1917" height="1078" alt="Screenshot 2026-08-07 111130" src="https://github.com/user-attachments/assets/c436ad01-6e5c-4489-83c7-8c02f3f8136b" />
<img width="1917" height="1078" alt="Screenshot 2026-08-07 113255" src="https://github.com/user-attachments/assets/a7d50027-59cc-49eb-bde2-4bc568e1507a" />
<img width="1917" height="1075" alt="Screenshot 2026-08-07 115208" src="https://github.com/user-attachments/assets/2b49b02e-2c10-41f3-85db-009af8f1a776" />
<img width="1917" height="1078" alt="Screenshot 2026-08-07 115248" src="https://github.com/user-attachments/assets/71a3e4f7-39a5-4c41-ac05-1e15fcc3e1e5" />
<img width="1917" height="1078" alt="Screenshot 2026-08-07 123414" src="https://github.com/user-attachments/assets/26c6cb53-c12c-4a72-996d-7ed0469239ac" />
<img width="1917" height="1078" alt="Screenshot 2026-08-07 123551" src="https://github.com/user-attachments/assets/0cc06b6d-97bb-476f-a0b8-c94eb70b744e" />

---

## ❗ Common Errors

### Directory Already Exists

```bash
mkdir: cannot create directory 'devops': File exists
```

### Directory Not Empty

```bash
rmdir: failed to remove 'devops': Directory not empty
```

### Incorrect Destination Path

```bash
mv: cannot move 'file1.txt': Not a directory
```

### Typing Mistake

```bash
ls-l: command not found
```

---

## 🎯 Key Takeaways

- Learned the difference between **Absolute Path** and **Relative Path**.
- Practiced essential Linux commands used in system administration.
- Improved confidence in managing files and directories using the Linux terminal.
- Gained hands-on experience working on an AWS EC2 Linux instance.
