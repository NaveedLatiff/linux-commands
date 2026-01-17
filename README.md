# linux-commands

pwd *(print working directory)

ls

cd

mkdir foldername

rmdir foldername


touch filename

rm filename

rm -r foldername


cp file.txt copy.txt

cp -r folder copyfolder


cat file.txt(Display content of file.txt)

cat file1.txt file2.txt > combined.txt (Combines file1.txt and file2.txt into a new file combined.txt)


echo "Hello, Linux!"

echo "This is my first file" > file1.txt (Use >> instead of > to append text instead of overwriting)


head file.txt (Shows the first few lines of a file)

head -n 5 file.txt (Show a specific number of lines)


tail file.txt (Shows the last few lines of a file)

tail -n 5 file.txt (Show a specific number of lines at last)


clear


whoami (Shows the current logged-in username)


man ls


history (Shows the list of commands you have typed before in the terminal
& 
You can reuse a command by typing !<number> like !3
)


sudo rm -r /protected_folder (Lets you run commands as an administrator (root)

Needed for commands that require higher privileges)


grep "hello" file.txt (Searches for the word “hello” inside file.txt)


find . -name "file.txt" (. → start search from current directory
-name "file1.txt" → look for files named file1.txt)

find /home/naveed -type d (Finds all directories (d) inside /home/naveed)

find . -name "*.txt" -exec cat {} \; (Finds all .txt files in current folder and subfolders
Executes cat on each file to show its contents)


awk '{print $1}' file1.txt ($1 → first column
Prints the first word/field of each line)

sed 's/Sarim/Naveed/' file.txt  (replace Sarim with Naveed but not replace in the file it is just output terminal
To replace directly in the file  use -i
)


tar

1. Make a folder archive (like zipping a folder):
tar -cvf myfolder.tar myfolder/
myfolder/ → folder you want to zip
myfolder.tar → the “zipped” file it creates
c → create
v → show what’s happening
f → specify file name


2. Look inside a tar archive (without extracting):
tar -tvf myfolder.tar
t → list contents


3. Extract/unzip the archive:
tar -xvf myfolder.tar
x → extract (unzipping)
After this, the folder comes back exactly as it was


4. With compression (smaller file like zip):
tar -czvf myfolder.tar.gz myfolder/
z → compress with gzip
Result → smaller .tar.gz file



sort file1.txt (can do in numeric reverse order etc )

sort -r file.txt > reverseorderfile.txt (can also save it in a new file)


uniq file.txt (remove duplicates)

uniq -c file.txt (count duplicates)


wc file1.txt (count lines,words and characters)


cut -d " " -f2 file.txt (Extract the 1st column
-d " " → delimiter (here a space)
-f1 → first field
) 


xargs (Takes output of one command and passes it as arguments to another command)
Example:

ls *.txt | xargs sed -i 's/Sarim/Naveed/g'


diff file1.txt file2.txt


ps (show running processes on the system)

kill <pid of the process>  (stops (terminates) a running process)
if not terminates then forced kill  by 
kill -9 pid 


scp (secure copy)
Can copy from local to remote and vice versa also
scp file.txt user@remote_host:/home/user/





hardlink(if change in the original file that will also reflect in softlink and if delete the original then the hardlink will work perfectly)

softlink (if change in the original file that will also reflect in softlink and if delete the original then the softlink also not work)

cut -b 1 file.txt (Give us the data in number of bytes we want)

tee:-

echo 'hello' | tee file.txt (it will aslo print hello on the terminal and save it to file also)

sort (It arranges the lines of a file in order, comparing characters from left to right, starting with the first character of each line)

learn vi/vim editor we can insert anything in the file then we can quit by clicking on esc key then write :wq



Now Login Related

* SSH is used to connect our computer to an EC2 instance through port 22. Usually, we can also change the port if needed

* SSH key (.pem) is a digital password used to securely connect your computer to an EC2 instance. The private key stays on your computer, and the public key is on the EC2. Only matching keys allow connection.



Disk Usage:-

df (Tell us how much space is free or use in the harddisk/partition of our system)

du (It tells about the space of the directory or file)


ls -a (Give the list of hidden folders)


Processes:-
ps (Show us current running processes)

top (Show all the processes)

kill (stops (terminates) a running process) if not terminates then forced kill by kill -9 pid

fuser filename (It tells which processes are using a file.)

nohup (It runs a command in the background and keeps it running even if the terminal or SSH session is closed.)

free (It tells how much RAM is free or used)

vmstat (It shows virtual memory, CPU, swap, I/O, and process statistics for system performance monitoring)



