# 🚀 Day 8 - Linux File Permissions & Ownership

## 📚 Topic

- Linux File Permissions (`chmod`)
- Changing File Ownership (`chown`)
- User & Group Recap
- Practicing Permissions on AWS EC2

---

## 📖 What I Learned

Today, I learned how Linux file permissions work (read/write/execute for owner, group, and others), how to change them using `chmod` (both symbolic and numeric modes), and how to change file/directory ownership using `chown`.

---

## 💻 Commands Used

### Create Files to Practice On

touch file1.txt
touch file2.txt
touch file3.txt
touch file4.txt

---

### View Permissions

ls -l

Shows permissions in the format `-rw-r--r--` → (owner)(group)(others), along with owner, group, size, and date.

---

### Change Permissions — Symbolic Mode

chmod u+rwx file1.txt   # add read, write, execute for the owner (user)
chmod g+rw file2.txt    # add read, write for the group
chmod o-r file3.txt     # remove read for others (others)

`u` = user/owner, `g` = group, `o` = others, `+` = add permission, `-` = remove permission.

---

### Change Permissions — Numeric Mode

chmod 730 file4.txt

Sets permissions directly using numbers:
- 7 = rwx (owner)
- 3 = -wx (group)
- 0 = --- (others)

---

### Create a Directory and Files Inside It

mkdir linux
cd linux
touch f1.txt
touch f2.txt
touch f3.txt

---

### Change Ownership — `chown`

chown mounika: linux           # invalid syntax — trailing colon with no group
chown mounika:devops f1.txt    # changes owner to mounika, group to devops

`chown <owner>:<group> <file>` changes both the owner and group of a file in one command.

---

### Change Ownership Recursively for a Directory

chown mounika:devops -R linux

The `-R` flag applies the ownership change to the directory **and all files inside it**.

---

## 🛠 Practical

- Created 4 practice files using `touch`.
- Used `chmod u+rwx`, `chmod g+rw`, and `chmod o-r` (symbolic mode) to add/remove specific permissions.
- Used `chmod 730` (numeric mode) to set exact permissions in one command.
- Created a `linux` directory with 3 files inside it.
- Created a new user (`mounika`) and a new group (`devops`).
- Used `chown mounika:devops` to change ownership of a single file.
- Used `chown mounika:devops -R linux` to change ownership of the whole directory recursively.
- Verified every change using `ls -l` before and after.

---

## ✅ Output Screenshots

Successfully practiced Linux file permissions (`chmod`) and ownership (`chown`) commands on an AWS EC2 instance.
<img width="1920" height="1080" alt="Screenshot 2026-09-01 144008" src="https://github.com/user-attachments/assets/d04fdfb3-1da7-496c-96c9-ff49f3353786" />
<img width="1920" height="1080" alt="Screenshot 2026-09-01 144029" src="https://github.com/user-attachments/assets/ea1a77cf-c0ab-45f0-9619-a4fb4269686e" />
<img width="1920" height="1080" alt="Screenshot 2026-09-01 144047" src="https://github.com/user-attachments/assets/0b81ca89-5e99-4a1b-90de-d536fc3f954c" />
<img width="1917" height="471" alt="Screenshot 2026-09-01 144149" src="https://github.com/user-attachments/assets/475386ac-e66f-4fea-9061-1476be658464" />




---

## ❗ Common Errors

### Invalid chown Spec

chown: invalid spec: 'mounika:'
Fix: a trailing colon with no group name is invalid — use `chown mounika:devops <file>` (owner**:**group), or just `chown mounika` if only the owner needs changing.

### Command Typo

bash: chwon: command not found
Fix: typo — the correct command is `chown`, not `chwon`.

### No Such File or Directory

chown: cannot access 'linux': No such file or directory
Fix: ran the command from the wrong directory — needed to `cd` into the parent folder where `linux` actually exists first.

### Unknown Command

bash: o-r: command not found
Fix: forgot to prefix with `chmod` — the correct command is `chmod o-r file3.txt`, not `o-r file3.txt` on its own.

---

## 🎯 Key Takeaways

- `ls -l` → view permissions, owner, and group of files/directories.
- `chmod u/g/o +/- r/w/x <file>` → symbolic mode, add/remove permissions per category.
- `chmod <number> <file>` → numeric mode (e.g. `730` = rwx for owner, -wx for group, --- for others).
- `chown <owner>:<group> <file>` → change both owner and group in one command.
- `chown <owner>:<group> -R <directory>` → change ownership recursively for a directory and everything inside it.
