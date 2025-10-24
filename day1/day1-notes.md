1.pwd - points to the current directory
/home/parth/labs/day1

2.ls -la  - list files incl hidden.
total 8
drwxr-xr-x 2 parth parth 4096 Oct 24 07:48 .
drwxr-xr-x 5 parth parth 4096 Oct 24 07:47 ..
-rw-r--r-- 1 parth parth    0 Oct 24 07:48 day1-notes.md

3.mkdir testdir && cd testdir then touch a.txt b.txt then ls — creates and lists files.
a.txt  b.txt

4.echo "hello" > a.txt then cat a.txt — show file contents.
hello

5.nano a.txt (or code a.txt) — open editor and add a line, save.
opens the editor in a new tab

6.cp a.txt ../copy_of_a.txt and mv ../copy_of_a.txt ../renamed.txt — copy & move.


7.rm a.txt — delete file (be careful).
deletes the file

8.chmod +x hello.sh (we’ll create later) — make executable.

9.grep -R "TODO" -n .. — search recursively.

10.find ~ -maxdepth 2 -type f -name "*.sh" — locate shell scripts.

11.ps aux | head -n 10 — process list
root           6  0.0  0.0   3104  1880 ?        Sl   06:29   0:00 plan9 --control-socket 7 --log-level 4 --server-fd 8 --pipe-fd 10 --log-truncate
root         195  0.0  0.0   4236  2560 ?        Ss   06:29   0:00 /usr/sbin/cron -f -P
message+     196  0.0  0.0   9824  5376 ?        Ss   06:29   0:00 @dbus-daemon --system --address=systemd: --nofork --nopidfile --systemd-activation --syslog-only
root         203  0.0  0.0  17964  8448 ?        Ss   06:29   0:00 /usr/lib/systemd/systemd-logind
root         205  0.0  0.1 1756096 12544 ?       Ssl  06:29   0:00 /usr/libexec/wsl-pro-service -vv
root         208  0.0  0.0   3160  2048 hvc0     Ss+  06:29   0:00 /sbin/agetty -o -p -- \u --noclear --keep-baud - 115200,38400,9600 vt220
root         227  0.0  0.0   3116  1920 tty1     Ss+  06:29   0:00 /sbin/agetty -o -p -- \u --noclear - linux


12.top or htop (if installed) — interactive process monitor (Ctrl+C to exit).
opens a monitor 
    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND                       
   6509 parth     20   0   73.1g 905412  65536 S   3.8   7.7   3:11.24 node                          
   7157 parth     20   0 1087548  80224  48640 S   1.2   0.7   0:14.34 node                          
   6448 parth     20   0   11.3g 140724  53248 S   0.9   1.2   0:46.82 node                          
   6481 parth     20   0 1333980  79040  48256 S   0.5   0.7   0:13.02 node                          
  11136 parth     20   0 1017036  60396  44160 S   0.5   0.5   0:02.61 node                          
  11144 root      20   0    3088   1168   1024 S   0.2   0.0   0:01.60 Relay(11145)    


13.df -h — disk usage human readable.
none            5.7G  564K  5.7G   1% /run
none            5.7G     0  5.7G   0% /run/lock
none            5.7G  112K  5.7G   1% /run/user
tmpfs           1.2G   20K  1.2G   1% /run/user/1000
drivers         953G  145G  809G  16% /usr/lib/wsl/drivers
none            5.7G     0  5.7G   0% /usr/lib/wsl/lib
none            5.7G  4.0K  5.7G   1% /mnt/wsl
none            5.7G  100K  5.7G   1% /mnt/wslg/versions.txt
none            5.7G  100K  5.7G   1% /mnt/wslg/doc
none            5.7G     0  5.7G   0% /usr/lib/modules/6.6.87.2-microsoft-standard-WSL2
C:\             953G  145G  809G  16% /mnt/c


14.du -sh ~/labs — folder size.
260K    /home/parth/labs

15.ifconfig or ip addr show — network interfaces.
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 65972  bytes 78685137 (78.6 MB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 65972  bytes 78685137 (78.6 MB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

16.ss -tulpn | head — listening services.
Netid State  Recv-Q Send-Q  Local Address:Port  Peer Address:PortProcess                          
udp   UNCONN 0      0          127.0.0.54:53         0.0.0.0:*                                    
udp   UNCONN 0      0       127.0.0.53%lo:53         0.0.0.0:*                                    
udp   UNCONN 0      0      10.255.255.254:53         0.0.0.0:*                                    
udp   UNCONN 0      0           127.0.0.1:323        0.0.0.0:*                                    
udp   UNCONN 0      0               [::1]:323           [::]:*                                    
tcp   LISTEN 0      511         127.0.0.1:38575      0.0.0.0:*    users:(("node",pid=6448,fd=22)) 
tcp   LISTEN 0      4096    127.0.0.53%lo:53         0.0.0.0:*                                    
tcp   LISTEN 0      4096       127.0.0.54:53         0.0.0.0:*                                    
tcp   LISTEN 0      511         127.0.0.1:3832       0.0.0.0:*    users:(("node",pid=12495,fd=22))


17.curl -I https://google.com — get headers (HTTP).
4_wxS2_twA' 'strict-dynamic' 'report-sample' 'unsafe-eval' 'unsafe-inline' https: http:;report-uri https://csp.withgoogle.com/csp/gws/other-hp
date: Fri, 24 Oct 2025 08:05:46 GMT
expires: Sun, 23 Nov 2025 08:05:46 GMT
cache-control: public, max-age=2592000
server: gws
content-length: 220
x-xss-protection: 0
x-frame-options: SAMEORIGIN
alt-svc: h3=":443"; ma=2592000,h3-29=":443"; ma=2592000


18.which python3 and python3 --version — confirm python.
which python3
/usr/bin/python3
python3 --version
Python 3.12.3

19.git --version — confirm git.
git version 2.43.0


echo "pwd -> $(pwd)" >> day1-notes.md