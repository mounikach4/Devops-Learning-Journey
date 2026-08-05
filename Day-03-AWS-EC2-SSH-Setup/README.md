# 🚀 Day 3 - Connecting to AWS EC2 via Git Bash (SSH)

Today, I learned how to securely connect to an AWS EC2 instance using Git Bash and SSH.

## 📚 What I Learned

- Generated an SSH Key Pair using Git Bash.
- Imported the Public Key into AWS EC2.
- Created a Security Group with SSH (Port 22) access.
- Launched an EC2 Instance (Amazon Linux/Ubuntu).
- Connected to the EC2 instance using SSH.

## 🛠️ Steps

### 1. Generate SSH Key Pair

ssh-keygen -f <key-name>
View the public key:

cat <key-name>.pub
---

### 2. Import Public Key into AWS

- EC2 Dashboard
- Network & Security → Key Pairs
- Actions → Import Key Pair
- Paste the public key and import

---

### 3. Create Security Group

Inbound Rule:
- Type: SSH
- Port: 22
- Source: Anywhere (IPv4)

---

### 4. Launch EC2 Instance

- Choose AMI (Amazon Linux/Ubuntu)
- Instance Type: t3.micro
- Attach Key Pair
- Attach Security Group
- Launch Instance

---

### 5. Connect to EC2

ssh -i <key-name> ec2-user@IP
## 💡 Key Takeaways

- Learned how SSH enables secure remote access.
- Understood the importance of Security Groups.
- Successfully connected to an AWS EC2 instance using Git Bash.
