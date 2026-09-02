# 🚀 Day 9 - SSH Key-Based Authentication for a Linux User on AWS EC2

## 📚 Topic

- SSH Key-Based Authentication
- Generating SSH Key Pairs
- Setting up `authorized_keys` for a New User
- Logging in Without a Password using SSH Keys

---

## 📖 What I Learned

Today, I learned how to set up **SSH key-based login** for a newly created Linux user on an AWS EC2 instance, instead of using password authentication. This is the standard, more secure way servers are accessed in real-world DevOps environments.

I practiced generating a key pair on my local machine, placing the public key on the server, and then logging in using the private key — no password required.

---

## 📝 Why Key-Based Login?

- 🔒 More secure than passwords (keys are much harder to brute-force).
- 🚫 No password is transmitted over the network at all.
- ⚙️ Standard practice for servers, CI/CD pipelines, and automation tools.
- 👤 Each user can have their own key pair for individual access control.

---

## 💻 Commands & Steps Used

### 1. Create a New Linux User

sudo su -
useradd mounika
id mounika

Creates a new user and confirms the UID/GID assigned to them.

---

### 2. Create the `.ssh` Directory for the User

cd /home/mounika
mkdir .ssh
cd .ssh

Every user needs their own `.ssh` folder to store their `authorized_keys` file.

---

### 3. Create and Edit the `authorized_keys` File

touch authorized_keys
vim authorized_keys

This file will hold the **public key** of anyone who is allowed to log in as this user.

---

### 4. Set Correct Permissions (Very Important)

chmod 600 authorized_keys
chmod 700 .ssh
chown mounika:mounika .ssh
chown mounika:mounika authorized_keys

SSH is strict about permissions:
- `.ssh` directory → `700` (only the owner can access it)
- `authorized_keys` file → `600` (only the owner can read/write it)
- Both must be owned by the correct user, not root

If permissions are too open, SSH will silently reject key-based login.

---

### 5. Generate an SSH Key Pair (on local machine)

ssh-keygen -f mounika

Generates a public/private key pair:
- `mounika` → private key (keep this safe, never share it)
- `mounika.pub` → public key (this goes on the server)

---

### 6. Copy the Public Key Content

cat mounika.pub

Copy this output and paste it inside the server's `authorized_keys` file (Step 3).

---

### 7. Login Using the Private Key

ssh -i mounika mounika@<server-ip>

The `-i` flag tells SSH to use a specific private key file instead of a password.

---

## 🛠 Practical

- Connected to AWS EC2 using SSH.
- Created a new user `mounika` and set up her home directory.
- Created `.ssh` folder and `authorized_keys` file with correct permissions.
- Generated a new SSH key pair (`ssh-keygen`) on the local machine.
- Copied the public key into the server's `authorized_keys` file.
- Successfully logged in as `mounika` using the private key — no password used.

---

## ✅ Output Screenshots

Successfully configured SSH key-based authentication for a new Linux user and logged in without a password.
## UserPhase:
<img width="1920" height="1080" alt="Screenshot 2026-09-02 200445" src="https://github.com/user-attachments/assets/d1fe58cf-5112-4f50-8201-48fcad05dce3" />

## AdminPhase:
<img width="1920" height="1080" alt="Screenshot 2026-09-02 200452" src="https://github.com/user-attachments/assets/27bdd5ab-1805-48b3-bf0f-34e921b32c79" />
<img width="1920" height="1080" alt="Screenshot 2026-09-02 195849" src="https://github.com/user-attachments/assets/9f2d0a72-8b5a-41ad-99ee-1e4496820f16" />
<img width="1920" height="1080" alt="Screenshot 2026-09-02 200502" src="https://github.com/user-attachments/assets/4fa502fb-021c-47ad-b96d-2aea24be0c07" />

---

## ❗ Common Errors

### Wrong Key Used First

ec2-user@<ip>: Permission denied (publickey,gssapi-keyex,gssapi-with-mic).

Happens when trying to log in as the wrong username with a key that isn't linked to that account.

### Permission Denied Due to Wrong File Permissions

Permission denied (publickey).

Usually caused by `.ssh` or `authorized_keys` having permissions that are too open, or being owned by the wrong user.

### Forgetting to `chown` After Creating Files as Root

Files created as `root` while setting up another user's `.ssh` folder must be `chown`'d back to that user, or SSH will reject the login.

---

## 🎯 Key Takeaways

- Learned how SSH key-based authentication works end-to-end.
- Understood why correct ownership and permissions on `.ssh` and `authorized_keys` are critical.
- Practiced generating key pairs with `ssh-keygen` and using `-i` to specify a private key during login.
- Gained hands-on experience setting up secure, passwordless access for a Linux user on AWS EC2.
