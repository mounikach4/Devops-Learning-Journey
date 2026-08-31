# 🚀 Day 7 - Linux User & Group Management + SSH Password Authentication

## 📚 Topic

- Linux User and Group Management
- Setting and Managing Passwords
- Enabling SSH Password Authentication
- Practicing User Management on AWS EC2

---

## 📖 What I Learned

Today, I learned how to create and manage users and groups in Linux, understand where user/group/password data is stored, and how to enable password-based SSH login (since Linux by default only allows key-based login).

---

## 💻 Commands Used

### Switch to Root User

sudo su -

Normal user (`$`) cannot perform admin tasks, so switch to root (`#`) to get full access.

---

### Create a User and a Group

useradd durga
groupadd devops

> **Note:** Creating a user automatically creates a primary group with the same name.

---

### Check User Details

id durga

Shows UID, GID, and the groups the user belongs to.

---

### Where User/Group/Password Data is Stored

/etc/passwd   → user information
/etc/group    → group information
/etc/shadow   → encrypted passwords

---

### Add User to Primary Group

usermod -g devops durga

Changes the user's primary group.

---

### Add User to Secondary Group

groupadd linux
usermod -aG linux durga

Adds the user to an additional (secondary) group without removing them from the primary one.

---

### Set/Change User Password

passwd durga

Prompts to enter and confirm a new password for the user.

---

### Enable SSH Password Authentication

vim /etc/ssh/sshd_config
# change: PasswordAuthentication yes

sshd -t                  # check config for syntax errors
systemctl restart sshd   # restart service to apply changes

By default, Linux only allows key-based SSH login. These steps enable password-based login too.

---

## 🛠 Practical

- Switched to root user using `sudo su -`.
- Created a new user (`durga`) and checked its details with `id`.
- Created and assigned a primary group (`devops`) using `usermod -g`.
- Created and assigned a secondary group (`linux`) using `usermod -aG`.
- Set a password for the user using `passwd`.
- Edited `/etc/ssh/sshd_config` to enable `PasswordAuthentication yes`.
- Verified the config with `sshd -t` and restarted SSH with `systemctl restart sshd`.
- Logged in as the new user from a local machine using `ssh durga@<ec2-ip>` with the password.

---

## ✅ Output Screenshots

Successfully practiced Linux user/group management and enabled SSH password authentication on an AWS EC2 instance.

<img width="1920" height="1080" alt="Screenshot 2026-08-31 202408" src="https://github.com/user-attachments/assets/dd942cfc-c6a7-48a3-b1c9-992c7c28f182" />
<img width="1920" height="1080" alt="Screenshot 2026-08-31 201623" src="https://github.com/user-attachments/assets/2d619414-62e2-47eb-9ec9-165ce1d36704" />
<img width="1920" height="1080" alt="Screenshot 2026-08-31 202356" src="https://github.com/user-attachments/assets/ab536444-9650-487b-9bff-81ec8fc8988f" />

---

## ❗ Common Errors

### Bad Password Warning

passwd: BAD PASSWORD: The password contains the user name in some form
Fix: this is just a warning, not a failure — a stronger password avoids it, but Linux still accepts it if retyped correctly.

### SSH Key Not Found

Warning: Identity file ec2-user@<ip> not accessible: No such file or directory.
Fix: the `-i` flag needs the key file name, not the username — correct usage is `ssh -i <keyfile> ec2-user@<ip>`.

---

## 🎯 Key Takeaways

- `useradd` / `groupadd` → create a user / group.
- `id <user>` → check UID, GID, and group membership.
- `/etc/passwd`, `/etc/group`, `/etc/shadow` → where user, group, and password data live.
- `usermod -g` → set primary group | `usermod -aG` → add secondary group.
- `passwd <user>` → set/change password.
- SSH defaults to key-based login → enable `PasswordAuthentication yes` in `/etc/ssh/sshd_config`, then run `sshd -t` and `systemctl restart sshd` to allow password login.
