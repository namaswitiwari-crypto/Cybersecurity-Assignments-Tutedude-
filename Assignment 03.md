# Assignment 03 – Linux Navigation & Hidden Files

## Task
- Navigate into the `loot` folder and identify the file inside.  
- Read the contents of the file located in the `loot` folder.  
- Discover and read the contents of the hidden file in the same folder.

## Approach
1. **Navigating to the loot folder**
   ```bash
   cd /home/student/loot
   ls
```
Found a file named readme.txt.

2. **Reading the file contents**
```
bash
cat readme.txt
```
3. **Listing hidden files**
```
bash
ls -al
```
Revealed a hidden file: .hidden_file.txt.

4. **Reading the hidden file**
```
bash
cat .hidden_file.txt
```

## Key Learnings
- The cd command is used to change directories, while ls lists files.
- Using ls -al reveals hidden files (those starting with a dot .).
- Hidden files often contain important information — in cybersecurity, attackers may hide artifacts this way.
- Combining navigation and inspection commands (cd, ls, cat) is essential for exploring and analyzing file systems.