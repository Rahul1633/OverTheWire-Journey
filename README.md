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
cat filename
```

### Bandit 5 → Bandit 6
**Concept Learned:**  Using ``find`` with multiple conditions. 

**Notes:** 
- `-type` command is used for file type and `-size` helps finding the required size (C stands for bytes).  
- `! -executable` this command ensures that it is not executable.

**Commands Practiced:** 
```bash
ls -la
cd
find -type f -size 1033c ! -executable
cat filename
```

### Bandit 6 → Bandit 7
**Concept Learned:**  Using ``find`` with user/group filtering and redirection.

**Notes:** 
- `find /` List all files/directories starting from root (/) . 
- `-group` and `user` these commands are used for filtering.
- `2>/dev/null` here 2 is stderror ,and dev/null is the blackhole of data where data discards itself and no log will be shown(suppresses permission errors).   

**Commands Practiced:** 
```bash
ls -la
find -size 33c -group groupname -user username 2>/dev/null 
cat filename
```

### Bandit 7 → Bandit 8
**Concept Learned:**  Searching inside files with `grep`. 

**Notes:** 
- The `grep` command in Linux is a command-line utility used for searching plain-text data sets for lines that match a regular expression. 

**Commands Practiced:** 
```bash
ls -la
grep pattern filename

```

### Bandit 8 → Bandit 9
**Concept Learned:** Finding unique strings in a file. 

**Notes:** 
- The `sort` command in Linux is a utility used to arrange lines of text from files or standard input into a specific order.
- `uniq` command is used to sort command in Linux is a utility used to arrange lines of text from files or standard input into a specific order.
- `|` The pipe is used to combine two or more commands. 

**Commands Practiced:** 
```bash
ls -la
sort filename | uniq -u

```

### Bandit 9 → Bandit 10
**Concept Learned:**  Extracting numbers with `strings` and filtering with `grep`. 

**Notes:** 
- `strings` extracts readable characters from a binary file.
- `grep` command is used to match the pattern or expression.
- `|` The pipe is used to combine two or more commands. 

**Commands Practiced:** 
```bash
ls -la
strings filename | grep pattern

```

### Bandit 10 → Bandit 11
**Concept Learned:**  how to do Base64 decoding .

**Notes:** 
- Use `base64` to encode data.
- Use `base64 -d` to decode data.

**Commands Practiced:** 
```bash
ls -la
base64 -d filename

```

### Bandit 11 → Bandit 12
**Concept Learned:**   ROT13 cipher decoding .

**Notes:** 
- ROT13 is a simple substitution cipher each letter is shifted by 13 positions in the alphabet.
- Applying ROT13 twice returns the original text.
- `tr` command performs substitution.

**Commands Practiced:** 
```bash
ls -la
cat filename | tr 'A-Za-z' 'N-ZA-Mn-za-m'

```

**Commands Explained:**  

- *Why Does This Mapping Work?*  
  - `N-ZA-M` maps uppercase letters `A-Z` by wrapping “N” to “A”.  
  - `n-za-m` does the same for lowercase letters `a-z`.  

- *Why NOT Use* `A-MN-Za-mn-z`?  
  - It doesn’t cover all 26 letters in order, causing mismatch in position mapping.  
  - The second set in `tr` must exactly match the length and order of the first set to work properly.

- **Example:**  
  - `Hello, World!` becomes `Uryyb, Jbeyq!`



### Bandit 12 → Bandit 13
**Concept Learned:**   File compression/decompression.

**Notes:** 
-File was repeatedly compressed in different formats
- Use `file` command each time to identify type, then extracted.

**Commands Practiced:** 
```bash
mkdir
cd
cp
mv
xxd -r filename > newfile
gzip -d filename
bzip2 -d filename
tar -x -v -f filename
cat filename
```


 
