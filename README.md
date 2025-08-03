# 🔐 OverTheWire – My Cybersecurity Learning Journey

This repository documents my progress through [OverTheWire Wargames](https://overthewire.org/wargames/).  
I’m using these challenges to strengthen my **Linux**, **networking**, and **problem-solving** skills.

---

## 🎯 Bandit Progress

### Bandit 0 → Bandit 1
**Concept Learned:** How to connect to a remote server using SSH and read a file from the home directory. 

**Notes:**   
- Learned to log in using the `ssh` command with username, hostname, and a custom port .  
- Also used `cat` to read the file content and `ls` to display all files.  

**Commands Practiced:**
```bash
ssh username@hostname -p port
ls
cat filename
```

### Bandit 1 → Bandit 2
**Concept Learned:** How to open and read files whose names start with a dash (-).  

**Notes:**   
- To open a '-' file use `cat <-`.  

**Commands Practiced:** 
```bash
ls
cat filename
```

### Bandit 2 → Bandit 3
**Concept Learned:** How to open files with spaces in their names.  

**Notes:**
- Filenames with **spaces** must be either quoted or have each space escaped (`"spaces in name"` or `spaces\ in\ name`).  
- Filenames starting with `-` can be misinterpreted as options; use `--` to stop option parsing or prefix with `./` to force it as a path.  
- Example safe targeting: `cat -- "filename with spaces"` or `cat ./--weird-name--`.  
- Used `ls -b` to reveal the exact filename (shows escaped characters) and relied on tab-completion to avoid typing mistakes.
  
**Commands Practiced:** 
```bash
ls -b
cat -- "--spaces in this filename--"
```

### Bandit 3 → Bandit 4
**Concept Learned:** How to find hidden files in a directory. 

**Notes:**   
- To find hidden files in a directory use `ls -la` to display all hidden files(start with '.').  
- Used basic `find` command to find the hidden files in the directory.
  
**Commands Practiced:** 
```bash
ls -la
cd
find 
cat filename
```

### Bandit 4 → Bandit 5
**Concept Learned:**  How to identify a file of a specific type among many files. 

**Notes:** 
- The most common data encodings that are human-readable are ASCII and Unicode.  
- The command `file ./*` uses the file command to determine the file type of all files and directories in the current directory.  

**Commands Practiced:** 
```bash
ls -la
cd
file ./*
cat filenam
```
