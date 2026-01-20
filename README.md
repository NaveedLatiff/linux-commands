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


User and Files Management


*System Level Commands

uname (shows the os name)

uptime (Shows how long the system has been running and how many users are currently active)

date

who (show active users with their activity),whoami (show a current username) 

which (shows the path of the executable file)

id (it shows current user  UID, GID and groups)

sudo (we get the temporary administrative rights(root) to run a command)

shutdown (safely turns off or restarts the system, optionally at a scheduled time)

reboot (restart the system immediately)

apt (used to install, update, upgrade, and remove software for debian/ubuntu)

yum (same like apt but for linux distribution(Red Hat/CentOS/Fedora))

dnf (same like apt but for Red Hat/CentOS/Fedora)

pacman (for Arch Linux / Manjaro)

portage (for Gentoo Linux)



User & Group Management system

useradd:-sudo useradd -m ahmed (creates a new user and automatically makes a home directory for them)

passwd(sudo passwd ahmed)

switch to ahmed (su ahmed)

exit (to comeback to ubuntu)

cat /etc/passwd (give the list of all user)

userdel (sudo userdel ahmed)


Group:-

cat /etc/group (list all the groups with its member)

To make a group (sudo groupadd it)

To add single user to group (sudo gpasswd -a ahmed it)

To add multiple user at a single time (sudo gpasswd -M ahmed,ali,murtuza)

To remove user (sudo gpasswd -d ahmed sudo)

To delete a group (sudo groupdel it) 


file permission commands:-


chmod 777 devops (Give rwx permission to user and group and other user)

ls -l (It shows files and directories in long format with permissions, owner, group, size, and date)

umask (Bydefault permission for nwely created file/directory)

chown naveed folder/filename (change ownership)

chgrp groupname folder/filename   (change group ownership)



compression command:-

zip -r devops.zip devops

unzip devops.zip

gzip compresses a single file not a directory and gunzip decompresses it

tar -cvzf devops.tar.gz devops (compress the file/folder but file extension is .tar.gz)

tar -xvzf devops.tar.gz (to unzip)


file transfer commands:-

scp (copy files from local to remote or remote to local)

rsync (it is used to synchronize or transfer files and directories between local and remote systems efficiently  just  copying the differences)


Networking Commands:-


ping  (used to check if servers or network devices are online, measure latency, and troubleshoot connectivity issues)

netstat (shows active network connections, listening ports, and which process is using which port)

ifconfig (shows network interfaces, IP addresses, netmask, broadcast, and data transmitted/received, used for monitoring and troubleshooting network)

traceroute (shows the path and hops(steps) a packet(request/message) takes to reach a server and the latency at each hop)

tracepath (it checks the path(like traceroute do)) along with the max packet size (MTU))

mtr (traceroute + ping)

nslookup (is used to find the IP address of a domain or the domain name of an IP, helping check DNS and network issues)

telnet (it is a protocol to connect to a remote server over a network (usually port 23) for testing or command access, but it is insecure)

hostname

ip (shows and manages network interfaces, IP addresses, and routes on the system)

iwconfig (shows the status and settings of wireless network interfaces like Wi-Fi, including network name, signal strength, and frequency)

ss (same like netstat) 

dig abc.com (is used to query DNS and get detailed information about a domain’s IP address and DNS records)

whois (tells the ownership and registration details of a domain or IP address)

nc (used to test ports, send/receive data, and check connectivity between systems)

arp (maps IP addresses to MAC addresses so that computers can send data to the correct device on a local network)

ifplugstatus (shows the status of all network interfaces, whether they are connected (working) or disconnected)

curl -X method api | jq (used to send request to APIs and jq give the data in formatted way)

wget link-address (to download files or content from internet)

watch (runs a command repeatedly and shows its output at regular intervals it is useful for live monitoring)

nmap (scans networks to detect open ports, running services, and operating systems for security and troubleshooting)

iptables (it is a firewall tool that controls which network traffic is allowed or blocked on a Linux system)

route  (shows or manages the paths (routes) packets take to reach different networks or hosts)


TEXT PROCESSING TOOLS:-


___AWK___  For structured Data


awk '{print $1,$2}' file.txt     
                                   
awk '$2 >=21 {print $1}' file.txt   

$1 → first column

$NF → last column

$(NF-1) → second last column            


**Remember AWK process line by line so every line has its own NF (NF means columns of the line)**

-sh-4.2$ awk 'NR>0 {print $0}' file.txt  ---$0 print all columns                                    

NR->Number of Row

awk '/CS/ {print$0}' file.txt  

awk '{i=1; while(i<=NF){print $i; i++}}' file.txt

awk '{for(i=1;i<=NF;i++){print $i}}' file.txt      

BEGIN runs after file start

END runs after file end

awk 'BEGIN {print "NAME AGE FIELD"} {print $0} END {print "ALL DONE..."}'  file.txt

awk 'NF>0 { $2 = $2 + 5; print $0 }' file.txt     
                  

**AWK have also builtin function like toupper,tolower etc**


awk -F',' '{print $1, $2}' file.txt   -F means tells the awk that the input is seperated by , in the file 

-sh-4.2$ awk 'BEGIN{OFS=":"} {print $1,$2}' file.txt  -->OFS is a output seperator

awk '{print substr($4,4,10)}' file.txt   --> start from 4 character and the length will be 10

                       

__SED__   For unstructured Data     -->Works directly on lines, doesn’t care about columns


For replace      sed 's/CS/MED/g' file.txt   -->g will replace all occurance

Delete Line    -sh-4.2$ sed '/IT/d' file.txt     Delete specific line    sed '2d' file.txt

sed -n 'p' file.txt    -n-> suppress automatic printing  

sed -n -e '1p' -e '3p' file.txt   -e allow multiples commands

sed '1a\Naveed 20 CS ' file.txt    a for append after the line or i for append before the line


__GREP__   specialized, super fast for just searching/filtering lines

grep -i 'iT' file.txt   -i for case sensitive

grep -c 'IT' file.txt   --count matching lines means how many lines contain IT

grep -v 'IT' file.txt     -v for all lines not containing IT

grep -r 'ERROR' /var/log/  ---search in all files that contains err in a directory

grep -e 'IT' -e 'CS' file.txt      -e for multiple commands

grep -n '' file.txt                                                 
 


 






 


