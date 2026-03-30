The Process Management commands 
ps -ef        # List all running processes
top           # Real-Time CPU & Process Usage
htop          # Interactive process viewer
kill <PID>    # Termiante process using PID
pkill<name>   # kill process by name
nice          # set process priority.
renice        # change running process priority
pstree        # Dispaly process in tree structures 

FIle system & Permissions
ls            # List files and directories
cd            # change directory
pwd           # present working directory
cp            # copy files /directories 
mv            # move or rename files
rm            # remove files / directories

Permission & Ownerships
chmod        # change file permisions
chown        # change file owner
chgrp        # chnage group ownership
umask        # default permission settings

 -rwx rw- r-- 
File Type    # - regular file; d directory; l symbolic link 
Permisison   # r Read        ; w Write      x Execute
rwx          # define the permission for user/owner
rw-          # define the permission for group
r--          # define the permisison for others

Network Trouble Shooting
ping         # check connectivity
traceroute   # Trace network path
mtr          # Real-Time  network analysis
netstat      # check open ports
ss           # chek open ports
ip addr      # show IP address
ip route     # show routhing tables
nslookup     # DNS lookup
dig          # Detailed DNS query
telnet       # test port connectivity
nc           # chekc port status
curl         # Test API/ HTTP response (API calling function)
wget         #  Downloads files
