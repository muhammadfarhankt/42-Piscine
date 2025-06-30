## Notes

You must not leave any additional files in your directory other than those specified in the assignment.

Terminal is nothing but another interface to do things on your machine

Directory means folder

pwd - print/present working directory -> displays the directory (or folder) you're currently in.

**cd - change directory**  
cd .. -> go back directory(One folder before current)  
cd ../.. -> Go back two folder

**ls** - List all files and directories  
ls -l -> List in detail

Tab key will auto complete file / folder names

**mkdir** - make directory  
Eg : mkdir folder1

**cat** - Print contents of file  
Eg : cat Readme.txt

**mv** - move files  
Eg : mv Readme.txt folder1  
You can move multiple files and give target folder at last  
mv file1 file2 file3 folder1

**cp** - copy files  
cp -r folder1 folder3  
-r means recursive it will be needed for folders

**Create a file**

1. touch - create an empty file (size 0)  
Eg : touch filename1

2. echo "" > test3  
It'll create a fie with size 1  
eventough it's empty it'll have fie ending data. That ie \0

3. mkfile <fileszie> <filename>
mkfile 25 test

**Soft link - symbolic link**  
ln -s test0 test6  
test6 -> test0

**Hard link**  - ln test3 test5  
This means test3 and test5 are the same file (two names, same inode).

**Change date and time**  
touch -t 202406012047 test0  
touch -h -t 202406012220 test6   -> -h for symbolic link

**Generate Key**  
ssh-keygen  
cat ~/.ssh/id_rsa.pub  
