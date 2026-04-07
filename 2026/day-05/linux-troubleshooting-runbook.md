Environment Basics 
* uname -a *
Linux aura-VB 6.17.0-19-generic #19~24.04.2-Ubuntu SMP PREEMPT_DYNAMIC Fri Mar  6 23:08:46 UTC 2 x86_64 x86_64 x86_64 GNU/Linux

* lsb_release -a *
No LSB modules are available.
Distributor ID:	Ubuntu
Description:	Ubuntu 24.04.4 LTS
Release:	24.04
Codename:	noble

* cat /etc/os-release *
PRETTY_NAME="Ubuntu 24.04.4 LTS"
NAME="Ubuntu"
VERSION_ID="24.04"
VERSION="24.04.4 LTS (Noble Numbat)"
VERSION_CODENAME=noble
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=noble
LOGO=ubuntu-logo

* cp /etc/hosts /tmp/runbook-demo/hosts-copy && ls -l /tmp/runbook-demo *
total 4
-rw-r--r-- 1 aura aura 222 Apr  7 06:01 hosts-copy
Learnt 
 Can system create directory?
 Can system copy file?
 Can system read/list file?

/Abhishek/learn_linux/day-05$ ps -o pid
    PID
   5653
  16189

:~/Abhishek/learn_linux/day-05$ ps -o pid,pcpu
    PID %CPU
   5653  0.0
  16196  0.0

~/Abhishek/learn_linux/day-05$ ps -o pid,pmem
    PID %MEM
   5653  0.0
  16199  0.0

/Abhishek/learn_linux/day-05$ ps -o pid,comm -p 1
    PID COMMAND
      1 systemd

$ free -h
               total        used        free      shared  buff/cache   available
Mem:           8.3Gi       1.2Gi       5.2Gi        39Mi       2.1Gi       7.0Gi
Swap:          4.0Gi          0B       4.0Gi
As a DevOps engineer, focus should be on available memory, not free memory, because cache memory can be reclaimed and used when required.

$ df -h
Filesystem      Size  Used Avail Use% Mounted on
tmpfs           846M  1.9M  844M   1% /run
/dev/sda2        49G   13G   35G  27% /
tmpfs           4.2G   84K  4.2G   1% /dev/shm
tmpfs           5.0M  8.0K  5.0M   1% /run/lock
tmpfs           846M  136K  846M   1% /run/user/1000
/dev/sr0         52M   52M     0 100% /media/aura/VBox_GAs_7.0.141

$ vmstat
procs -----------memory---------- ---swap-- -----io---- -system-- -------cpu-------
 r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st gu
 7  0      0 5304392  57892 2288272    0    0   411    17  504    0  0  0 99  0  0  0
 vmstat shows processes, memory usage, swap activity, disk I/O, system interrupts, and CPU utilization to help identify system performance issues.

 $ ss -tulpn
Netid          State           Recv-Q          Send-Q                   Local Address:Port                    Peer Address:Port         Process          
udp            UNCONN          0               0                           127.0.0.54:53                           0.0.0.0:*                             
udp            UNCONN          0               0                        127.0.0.53%lo:53                           0.0.0.0:*                             
udp            UNCONN          0               0                              0.0.0.0:5353                         0.0.0.0:*                             
udp            UNCONN          0               0                              0.0.0.0:54517                        0.0.0.0:*                             
udp            UNCONN          0               0                                 [::]:46287                           [::]:*                             
udp            UNCONN          0               0                                 [::]:5353                            [::]:*                             
tcp            LISTEN          0               4096                         127.0.0.1:43167                        0.0.0.0:*                             
tcp            LISTEN          0               5                              0.0.0.0:4330                         0.0.0.0:*                             
tcp            LISTEN          0               4096                         127.0.0.1:631                          0.0.0.0:*                             
tcp            LISTEN          0               4096                     127.0.0.53%lo:53                           0.0.0.0:*                             
tcp            LISTEN          0               4096                        127.0.0.54:53                           0.0.0.0:*                             
tcp            LISTEN          0               511                            0.0.0.0:80                           0.0.0.0:*                             
tcp            LISTEN          0               5                              0.0.0.0:44321                        0.0.0.0:*                             
tcp            LISTEN          0               4096                             [::1]:631                             [::]:*                             
tcp            LISTEN          0               5                                 [::]:4330                            [::]:*                             
tcp            LISTEN          0               511                               [::]:80                              [::]:*                             
tcp            LISTEN          0               5                                 [::]:44321                           [::]:*                             


$ netstat -tulpn
(Not all processes could be identified, non-owned process info
 will not be shown, you would have to be root to see it all.)
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name    
tcp        0      0 127.0.0.1:43167         0.0.0.0:*               LISTEN      -                   
tcp        0      0 0.0.0.0:4330            0.0.0.0:*               LISTEN      -                   
tcp        0      0 127.0.0.1:631           0.0.0.0:*               LISTEN      -                   
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      -                   
tcp        0      0 127.0.0.54:53           0.0.0.0:*               LISTEN      -                   
tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN      -                   
tcp        0      0 0.0.0.0:44321           0.0.0.0:*               LISTEN      -                   
tcp6       0      0 ::1:631                 :::*                    LISTEN      -                   
tcp6       0      0 :::4330                 :::*                    LISTEN      -                   
tcp6       0      0 :::80                   :::*                    LISTEN      -                   
tcp6       0      0 :::44321                :::*                    LISTEN      -                   
udp        0      0 127.0.0.54:53           0.0.0.0:*                           -                   
udp        0      0 127.0.0.53:53           0.0.0.0:*                           -                   
udp        0      0 0.0.0.0:5353            0.0.0.0:*                           -                   
udp        0      0 0.0.0.0:54517           0.0.0.0:*                           -                   
udp6       0      0 :::46287                :::*                                -                   
udp6       0      0 :::5353                 :::*                                -                   


$ iostat
Linux 6.17.0-20-generic (aura-VB) 	04/07/2026 	_x86_64_	(4 CPU)

avg-cpu:  %user   %nice %system %iowait  %steal   %idle
           0.18    0.00    0.46    0.06    0.00   99.30

