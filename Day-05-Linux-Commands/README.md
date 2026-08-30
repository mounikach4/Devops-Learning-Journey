# 🚀 Day 5 - Linux Commands

## 📚 Topic

- Linux Text Processing Commands
- File Content Viewing & Filtering
- Downloading Files from the Internet
- Practicing Linux Commands on AWS EC2

---

## 📖 What I Learned

Today, I practiced essential Linux commands on an AWS EC2 instance, focused on reading, filtering, and extracting content from files, and on fetching files from the internet.

I worked with a sample file (`file1.txt`) to explore searching, viewing partial content, and extracting specific columns/characters from text.

---

## 💻 Commands Used

### List Files & Directories

```bash
ls -l
```

Displays detailed information about files (permissions, owner, size, date).

---

### Search Text in a File

```bash
grep words file1.txt
```

Searches `file1.txt` for the word `words` and prints every matching line, highlighting the match.

---

### View Beginning of a File

```bash
head file1.txt      # prints first 10 lines by default
head -2 file1.txt   # prints only the first 2 lines
```

---

### View End of a File

```bash
tail file1.txt
```

Prints the last 10 lines of a file by default.

---

### Extract Sections from a Line

```bash
cut -d "," -f1 file1.txt   # cut using "," as delimiter, print field 1
cut -c 1 file1.txt         # cut character 1 from each line
```

---

### Fetch a File from the Internet

```bash
curl https://raw.githubusercontent.com/mounikach4/Devops-Learning-Journey/refs/heads/main/Day-01-SDLC-DEVOPS/README.md
```

Prints the remote file's content directly to the terminal.

```bash
wget https://raw.githubusercontent.com/mounikach4/Devops-Learning-Journey/refs/heads/main/Day-01-SDLC-DEVOPS/README.md
```

Downloads and saves the file locally (unlike `curl`, which just prints it).

---

### Print Text to Terminal

```bash
echo "I'm learning DevOps"
```

---

### Create an Empty File

```bash
touch f1.txt
```

---

### Write Content to a File

```bash
cat > f1.txt
I'm learning crouse DevOps,
Now I'm learning linux
^C
```

`cat > file` lets you type content directly into a file (Ctrl+C to stop).

---

### Column-Based Text Processing

```bash
awk -F' ' '{print $1}' f1.txt
```

Splits each line by space (`-F' '`) and prints the first field (`$1`).

---

## 🛠 Practical

- Connected to AWS EC2 using SSH.
- Searched and filtered text using `grep`.
- Viewed partial file content using `head` and `tail`.
- Extracted specific fields/characters using `cut`.
- Downloaded a remote file using `curl` and `wget`.
- Created and wrote to files using `touch` and `cat`.
- Processed column-based text using `awk`.

---

## ✅ Output Screenshots

Successfully practiced Linux text-processing commands on an AWS EC2 instance and gained hands-on experience filtering and extracting file content.
<img width="1920" height="1080" alt="Screenshot 2026-08-29 132208" src="https://github.com/user-attachments/assets/8b6d337f-8e35-4a15-b44c-a575b8e1b32a" />
<img width="1920" height="1080" alt="Screenshot 2026-08-29 132133" src="https://github.com/user-attachments/assets/ac78de52-0199-48db-a238-1b884091d450" />
<img width="1920" height="1080" alt="Screenshot 2026-08-29 134024" src="https://github.com/user-attachments/assets/0710aa05-a7e9-4f92-8775-14fc0bd1361e" />
<img width="1920" height="1080" alt="Screenshot 2026-08-29 134045" src="https://github.com/user-attachments/assets/e1211a88-cf86-453c-8bf1-cd58677d3097" />

---

## ❗ Common Errors

### Wrong Command Name

```bash
trail: command not found
```
Fix: the correct command is `tail`, not `trail`.

### File Not Found

```bash
cut: file.txt: No such file or directory
```
Fix: filename was `file1.txt`, not `file.txt`.

### Typing Mistake in Filename

```bash
head: cannot open 'file1,txt' for reading: No such file or directory
```
Fix: used a comma instead of a dot — correct filename is `file1.txt`.

---

## 🎯 Key Takeaways

- `grep` → search text inside a file.
- `head` / `tail` → view the start/end of a file.
- `cut` → extract specific columns or characters.
- `curl` vs `wget` → curl prints to screen, wget downloads to disk.
- `cat >` → quick way to create/write into a file.
- `awk` → powerful column-based text processing.
- Gained hands-on experience working on an AWS EC2 Linux instance.
