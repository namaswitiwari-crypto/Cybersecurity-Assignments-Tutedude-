Assignment 02 – Linux File Permissions

## Task
- Understand how permissions work in Linux.  
- Modify permissions to access a restricted file.  
- Read the content of `/home/student/practice/restricted_file.txt`.

## Approach
1. **Navigating to the directory**
   ```bash
   cd /home/student
   ls -al
```
- Listed files with detailed permissions to analyze ownership and access rights.

2. **Changing permissions**

```
bash
chmod 777 /home/student/practice/restricted_file.txt
```
Modified the file’s permissions to allow read, write, and execute access for all users.

3. **Reading the restricted file**

```
bash
cat /home/student/practice/restricted_file.txt
```
Output:
```
Code
flag{you_understood_permissions}
```

## Key Learnings
- Linux permissions are defined by three sets: owner, group, others.
- The chmod command is used to change file permissions.
- Granting 777 gives full access to everyone, but in real-world scenarios this is insecure — permissions should be set carefully.
- Understanding permissions is crucial in cybersecurity, as misconfigured permissions can lead to privilege escalation or data leaks.