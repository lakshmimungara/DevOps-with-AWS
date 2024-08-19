Day-3 session-3(14/08/2024)
----------------------------

Recap
------
1. created keys
2. imported public key into AWS
3. Created Security group
4. created EC2 instance 
5. connected with EC2 instance
6. Practiced few commands
7. Absolute path and Relative path
8. ports and protocols eg: SSH protocol uses port no 22

<command-name><options><inputs>
-<single-chat>
--<word>


## Syntax to connect to instance:
```
ssh -i <private-key-path> ec2-user@IP address
```
 GitBash is the client to connect to linux server.
 Open GitBash, enter the file path cd /c/devops/daws-81s.
 enter the synatx to connect - $ ssh -i demo-key.pem ec2-user@52.205.59.244.
 Here, Ip address is 52.205.59.244
 - In the previous class we have learned some commands like,
1. clear
2. pwd  = present working directory
3. cd   = change directory
4. ls -l = list out all the lengthy files with details
5. ls -ltr = list out all the files with details based on time in reverse order
6. ls -la  = list out all the files with details and it shows all the hidden files as well
7. cat  = It shows/ displays the contents and usefull to create a content inside a file
8. touch  = which is used to create a file 
9. mkdir  = It is used to create directories
10. rmdir = It removes the directories
11. rm    = It removes the files 
12. mv   = It moves one file to another

1. uname = It tells about the what your system kernel
2. uname -a = It gives all the information like; OS name, computer name, architecture 
3. uname --help = to get total system information

How to copy files?
------------------
- In windows, we need which file to copy and where to copy... we use ctrl+c for copy and ctrl+v for paste
- Here, in linux we use the command
```
cp <source-file> <destination-file>
```
- suppose we have a root folder, in that we have a file named password in a directory named etc
- /etc/passwd
- cp /etc/passwd users 
- ls -l = -rw-r--r--. 1 ec2-user ec2-user 1436 Aug 15 01:31 users
- Here, we are copying /etc/passwd file deatils to users file. we can give same file name or different file name
- cp /etc/passwd passwd  = here we are copying with the same file name, the result shows like this 
- -rw-r--r--. 1 ec2-user ec2-user 1436 Aug 15 01:35 passwd
- -rw-r--r--. 1 ec2-user ec2-user 1436 Aug 15 01:31 users

how to cut the file?
--------------------
- we are cutting the file from one location and pasting into another location
- for example, we have created one directory using mkdir devops. so, here the task is to cut the users file and move it into the devops directory
- So, this is called cutitng the file or reanming the file

How to search a particular word in a file?
-------------------------------------------
- synatx for the command:
  ```
   grep <word-to-find> <file>
  ```
for example; grep sbin passwd
- The word in the file gets highlighted
- Linux is case-sensitive 
- If we want the insensitive words without following the case-sensitive or not

what if i want to replace a word with another word for all occurences?
-----------------------------------------------------------
- command is,
```
:s/which-word/what-you-want/g
```
- eg:    :s/sbin/SBIN/g
- It replaces the word for all occurence

what if i want to replace a word with another word for all occurences in a particular line?
-----------------------------------------------------------
- command is,
 ```
  :<line-number>s/which-word/what-you-want/g
```
- eg:    :3s/sbin/SBIN/g
- It replaces the word for all occurence in a particular given line 

what if i want to replace everything/ everyword/ all occurences in a file?
-----------------------------------------------------------
- The command is,
```
 :%s/which-word/what-you-want/g
```
- eg:   :%s/sbin/SBIN/g
- It replaces all occurences in a file 


To findout the replaced word or any word:
-------------------------------------------
- command is,
```
:/word-you-want
```
- eg;   :/SBIN

What if I want to delete a particular line in a file?
-----------------------------------------------------
- command is,
```
 :<line-number>d
```
- here d represents the delete 
-  eg:  :2d --> which deletes the second line in a file

Esc mode:
----------
- If by mistake you have deleted something, then press symbol 'u' to undo 
- u --> undo
- shift+g --> which goes from first to bottom 
- gg --> which goes from bottom to top
- yy --> which copies the particular line where cursor is located 
- p --> whatever you have copies by typing yy that is pasted in the next line of it 
- 10p --> 10 times paste
- dd --> deletes a particular line where cursor is placed 

what if i want to paste the copied line 10 times?
-------------------------------------------------
- After copying,
```
press <count>p
```
- eg:   10p --> which paste the same line 10 times 

what if I want to delete a particular line in a file?
------------------------------------------------------
- press 'dd' by placing cursor at particular line in Esc mode

Insert mode:
--------------
- This is only for insertion



Permissions  - imp for interviews
----------------------------------
- Any OS consists of read,write and execute modes

How to setup permissions for any file is important?
----------------------------------------------------
for example;  -rw-r--r--
- It divides into three parts 
- hyphen(-)==> It denotes the file 
- rw- ==> who is the owner of the file --> user(u)
- r-- ==> which group he belongs to --> group(g)
- r-- ==> others  --> others(o)

for example:  
- Suppose, sivakumar is the owner and he is devops engineer
- Ramesh and Suresh are the team members who works with sivakumar and they also devops engineers
- Raheem and Robert are development team 
- So, rw-- permissions for sivakumar and he has read and write options 
- r-- permission for Ramesh and Suresh and they have only read access
- r-- permissions for others like Raheem and Robert and they have only read access 


** when you don't assign a user to any group, his group is also same as his username 

who can change the permissions?
--------------------------------
- Either owner or root user/admin can change the permissions 
- command is, chmod
-  for adding permissions, we use '+' symbol
-   ommand is, chmod o+w <file-name>  --> here, 'o' is others and 'w' is for write permissions
eg:  chmod o+w session-3.txt
-  or removing permissions, we use '-' symbol
-   command is,  chmod o-rwx <file-name>   --> here 'o' is others, rwx is for read,write and execute permissions
eg:   chmod o-rwx session-3.txt


what if I want to give all permissions to all members?
-------------------------------------------------------
- command is,
```
chmod ugo+rwx <file-name>
```
- here 'ugo' is for user,group and others and rwx is for read,write and execute permissions
eg: chmod ugo+rwx session-3.txt


** imp for interviews
---------------------
- R --> 4
- W --> 2
- X --> 1
- total add up to 7(which means all permissions)
- 777 --> all access to everyone
- 750 --> all access to owner, rx for group, 0 for others
eg: chmod 750 session-3.txt




Q/A session:
------------
1. echo Hello > hello.txt 
   cat hello.txt  --> Hello

2. ssh-keygen --help 

3. VI is already installed in systems and VIM is installed by default.. these are almost same only the change is colors becoz, VI is visually improved version 

4. mv devops devops-1(to move one folder to another folder)
