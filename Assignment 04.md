# Assignment 04 – Bash Scripting Basics

## Task
- Write a bash script (`read_secret.sh`) that reads the content of `secret.txt`.  
- Store the content in a variable and print it on the terminal.  
- Understand file permissions and script execution in Linux.

## Approach
1. **Creating the script**
```
bash
nano read_secret.sh
```
inside script:
```
bash
#!/bin/bash
SECRET_CONTENT=$(cat secret.txt)
echo "$SECRET_CONTENT"
```

2. **Making the script executable**
```
bash
chmod +x read_secret.sh
```

3. **Running the script**
```
bash
./read_secret.sh
```
- Faced permission issues when trying to read secret.txt.
- Verified file permissions using ls -al.

4. **Executing helper binary**
```
bash
./run_secret
```

## Key Learnings
- Bash scripts can automate tasks like reading and printing file contents.
- Variables in bash (VAR=$(command)) store command outputs for later use.
- File permissions can prevent direct access — understanding ownership and rights is critical.
- In cybersecurity, scripting is essential for automation, log analysis, and penetration testing workflows.