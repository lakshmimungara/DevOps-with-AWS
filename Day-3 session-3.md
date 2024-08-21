Day-3 Session-3 (14/08/2024)
----------------------------
Recap
------
Key Actions:
------------
1. Created keys
2. Imported public key into AWS
3. Created Security Group
4. Created EC2 instance
5. Connected with EC2 instance
6. Practiced commands
7. Learned about absolute and relative paths
8. Explored ports and protocols (e.g., SSH protocol uses port 22)
   
Syntax to Connect to an EC2 Instance
------------------------------------
```
ssh -i <private-key-path> ec2-user@<IP-address>
```
Example:
```
ssh -i demo-key.pem ec2-user@52.205.59.244
```
> GitBash is used as the client to connect to the Linux server.

Basic Commands:
-----------------
1. **clear** - Clears the terminal screen.
2. **pwd** - Present Working Directory.
3. **cd** - Change Directory.
4. **ls -l** - List all files with detailed information.
5. **ls -ltr** - List files with details based on time in reverse order.
6. **ls -la** - List all files with details, including hidden files.
7. **cat** - Display file contents and create content inside a file.
8. **touch** - Create a new file.
9. **mkdir** - Create directories.
10. **rmdir** - Remove directories.
11. **rm** - Remove files.
12. **mv**- Move or rename files.

System Information:
-------------------
1. **uname** - Shows system kernel information.
2. **uname -a** - Provides complete system information including OS name, computer name, and architecture.
3. **uname --help** - Displays help for the uname command.

File Operations:
----------------
- **Copy Files:**
```
cp <source-file> <destination-file>
```
Example:
```
cp /etc/passwd users
```

- **Move/Cut Files:**
```
mv <source-file> <destination-directory>
```

Searching and Replacing in Files
----------------------------------
- **Search for a Word:**
```
grep <word-to-find> <file>
```
Example:
```
grep sbin passed
```

- **Replace a Word:**
```
:s/<old-word>/<new-word>/g
```
Example:
```
:s/sbin/SBIN/g
```

- **Replace a Word in a Specific Line:**
```
:<line-number>s/<old-word>/<new-word>/g
```
Example:
```
:3s/sbin/SBIN/g
```
- **Replace a Word in the Entire File:**
```
:%s/<old-word>/<new-word>/g
```
Example:
```
:%s/sbin/SBIN/g
```
- **Find the Replaced Word:**
```
:/<word-to-find>
```
Example:
```
:/SBIN
```
- **Delete a Specific Line:**
```
:<line-number>d
```
Example:
```
:2d
```

VI Editor Commands:
----------------------
1. **Undo**: u
2. **Go to Bottom**: Shift+g
3. **Go to Top**: gg
4. **Copy Line**: yy
5. **Paste**: p
6. **Paste Multiple Times**: <count>p (e.g., 10p)
7. **Delete Line**: dd

Permissions:
--------------
- File Permission Representation: **-rw-r--r--**

- **hyphen(-)** - File type
- **rw-** - User (owner) permissions
- **r--** - Group permissions
- **r--** - Others permissions

**Change Permissions:**
------------------------
- **Add Permissions:**
```
chmod o+w <file-name>
```
- **Remove Permissions:**
```
chmod o-rwx <file-name>
```
- **Give All Permissions to All Members:**
```
chmod ugo+rwx <file-name>
```
**Numeric Permissions:**

- 4 - Read (R)
- 2 - Write (W)
- 1 - Execute (X)
- 777 - All access to everyone
- 750 - All access to owner, read and execute for group, no access for others
  
**Q/A Session**
- echo Hello > hello.txt followed by cat hello.txt displays "Hello".
- ssh-keygen --help displays help for the ssh-keygen command.
- VI and VIM are similar; VIM is an improved version of VI with additional features like color.
**To move a directory:**
- mv devops devops-1
