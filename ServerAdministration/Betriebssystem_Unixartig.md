# Linux

## Measruing
$>  iostat
iostat gibt eine Reihe von Werten aus und wird typischerweise mit zwei numerischen Parametern aufgerufen:
Beispiel: iostat 1 5
1 -> die Werte werden jede Sekunde erneut gemessen und ausgegeben
5 -> die Werte werden 5x ausgegeben, danach wird das Programm beendet

$>  iotop
Das Linux Monitoring-Tool iotop zeigt die aktuellen I/O Transferraten für die gerade laufenden Prozesse/Threads. Es verwendet dabei die I/O Usage Informationen des Linux Kernels (erfordert Linux Kernel Version 2.6.20 oder neuer).

$>  vmstat
Ist ein Computer zu langsam, sind die Ursachen oft nicht einfach zu ermitteln. Ist es eine zu langsame Festplatte, ist der Arbeitsspeicher zu klein oder ein überlasteter Prozessor? vmstat gibt tabellarisch Auskunft über Prozesse, Arbeitsspeicher, Auslagerung sowie Festplatten- und Prozessor-Aktivitäten. vmstat ist somit ein Hilfsmittel, um die Ursache eines Engpasses ermitteln zu können.

$>  netstat
erzeugt eine Anzeige, in der Netzwerkstatus und Protokollstatistiken aufgeführt werden

$>  ss
is used to dump socket statistics. It allows showing information similar to netstat.  It can display more TCP and  state information than other tools.

$>  iptraf
IPTraf ist ein konsolenbasiertes Netzwerk-Statistikprogramm für Linux. Es sammelt unter anderem Informationen über TCP-Verbindungen und zählt Pakete und Bytes

$>  pstree, ps
pstree steht für Process Tree. pstree stellt alle aktuell laufenden Prozesse in einer übersichtlichen Baumstruktur da.

$>  w
w zeigt Informationen über Benutzer an, die aktuell angemeldet sind

$>  lsof
steht für list open files und ist ein Hilfsprogramm, welches Informationen über geöffnete Dateien liefert. Dies hört sich im ersten Moment unspektakulär an, jedoch sollte man dabei bedenken, dass unter unixartigen Betriebssystemen, also auch (Ubuntu) Linux, alles eine Datei ist. So werden auch Blockgeräte (=Laufwerke), Netzwerkports usw. über Dateien angesprochen. D.h. lsof kann ein sehr mächtiges Tool zur Überwachung und Analyse des Systems sein.

$>  top   htop
zeigt eine dynamische Übersicht der laufenden Prozesse (siehe auch ps) sowie der belegten Systemressourcen an. Gegenüber dem Klassiker top bietet htop Prozessmanager jedoch einige Komfortfunktionen.

$>  uptime
Der Befehl uptime gibt aus, wie lange der Rechner seit dem letzten Bootvorgang läuft, wie viele Benutzer zur Zeit eingeloggt sind und die mittlere Systemauslastung der letzten Minute, 5 Minuten und 15 Minuten.

$>  sar
Sie können den folgenden Befehl ausführen, um die CPU-Auslastung 4 Mal alle 1 Sekunde zu überwachen.
sar 1 4

$>  swap
Swapfile used


### Dateityp einer unbekannten Datei finden

$> exiftool <file> 

### ssh-key generieren

$> ssh-keygen -t rsa -b 4096 -C "username"

### Fingerprint auf dem Zielsystem erzeugen

$> ssh-keygen -l -E md5 -f <(ssh-keyscan localhost 2>/dev/null)
	
### ssh-Tunnel aufbauen - autossl

$> ssh -i /root/.ssh/<folder> -N -L 3317:<IP Tunnel-Server>:3306 <username>@<Ziel-IP> 
	
$> mysql -u <mysql-username> -p -P 3317 -h 127.0.0.1

### autossh

autossh kann unter /etc/systemd/system eingestellt werden \\

### Resize partition
	
$> fdisk -l 

$> pvs 
	
$> pvcreate /dev/sdc
	
$> vgs
	
$> vgextend VG_INT /dev/sdc

$> lvs
	
$> lvextend -L +10G /dev/sda1/data

$> resize2fs /dev/sda1/data

### Zeige alle Prozesse

$> ps -ef

### Gitlab voll

$> project = Project.find\_ by\_full\_path('lifestyle/magento-enterprise') 
	
$> builds\_with\_artifacts =  project.builds.with\_downloadable\_artifacts 
	
builds\_to\_clear = builds\_with\_artifacts.where("finished\_at < ?", 1.days.ago) 
	
builds\_to\_clear.find\_each do |build| 
	
  build.artifacts\_expire\_at = Time.now 
	
  build.erase\_erasable\_artifacts!


### Memory Limit von php erhöhen
	
/etc/php/7.2/fpm/php.ini

### Wechsle zu Linux Default Browser
	
$> xdg-mime default google-chrome.desktop text/html
	
$> xdg-mime default google-chrome.desktop x-scheme-handler/http
	
$> xdg-mime default google-chrome.desktop x-scheme-handler/https
	
$> xdg-mime default google-chrome.desktop x-scheme-handler/about 

## Datenbankbereinigung Akeneo

$> php bin/console pim:installer:db --catalog vendor/akeneo/pim-community-dev/src/Akeneo/Platform/Bundle/InstallerBundle/Resources/fixtures/minimal
	
$> php bin/console pim:user:create
 
### Restarte Firewall
$>  etc/init.d/netfilter status/off/start
## Zeige IP-Tables
$> iptables -L -n

### Whitelist von IP-Tables
/opt/solr-6.6.2/server/etc/jetty.xml
### finde text in allen files
$> find . -type f -exec grep iwas {} -ls \;
### Check Zertifikate
$> openssl x509 -in cert.crt -noout -text
### Route anlegen
$> route add -net 192.168.1.0 netmask 255.255.255.0 gw 192.168.0.5


### Colorscheme im vim-Editor ändern
$> echo "colorscheme industry" >> /root/.vimrc

### TSM-Mobaxterm
starte mobaexterm und klicke auf "X server" 
	
/opt/tivoli/tsm/client/ba/bin
	
$> export DISPLAY=private\_IP\_eigner\_Rechner:0.0 
$> ./dsmj oder ./dsmc
	
### Zeige offene Ports
$> ss -ltn 

### Iptables zeitweise alles erlauben
iptables-save > /root/current.ipt
iptables -P INPUT ACCEPT; iptables -P OUTPUT ACCEPT
iptables -F INPUT; iptables -F OUTPUT
ping -c 3 google.com
iptables-restore < /root/current.ipt
rm -f /root/current.ipt

### Neuen Nameserver auf Server hinterlegen
$> echo "nameserver 8.8.8.8" | sudo tee /etc/resolv.conf > /dev/null
	
### Standardverzeichnis Windows für Comandlets
	C:\Users\doerflet\AppData\Local\Microsoft\WindowsApps
	
### Eintrag in IPtables
$> iptables -A INPUT -s <IP>/32 -d 217.145.101.37/32 -i eth0 -p tcp -m tcp --dport 3306 -m state --state NEW -j ACCEPT
### Port-Forwarding
Port forwarding also called “port mapping” commonly refers to the network address translator gateway. 
	
changing the destination address and/or port of the packet to reach a host within a masqueraded, typically private, network. 

iptables -A PREROUTING -i eth0 -p tcp -m tcp --dport 7009 -j DNAT --to-destination <IP>:8983 
	
iptables -A FORWARD -p tcp -d <IP> --dport 8983 -j ACCEPT 
	
iptables -A FORWARD -j NIRWANA

### Package hinzufügen
$> dotnet add package Microsoft.Azure.Cosmos --version 3.11.0
### Git zertifikat
$> export GIT\_SSL\_NO\_VERIFY=1
### Interface - Netzwerkadaper einrichten
$> vi /etc/netfilter.d/interfaces 
	
DEV\_LOC=eth1 
	
$> vi /etc/network/interfaces 
	
allow-hotplug eth1 
	
iface eth1 inet static 
	
        address <IP>
	
        netmask <IP>
	
        network <IP>
	
        broadcast <IP>

$> lspci 
	
$> vi /etc/network/interfaces 
	
$> /etc/init.d/networking restart 

### Aktive TCP-Verbindungen
	
$> netstat -a | grep ESTABLISHED

### ARP
Über das (Reverse) Address Resolution Protocol (ARP) tauschen die einzelnen Hosts Informationen über MAC-Adressen und IP-Adressen aus.
### Sniffing genauen Packetinhalt
$>  tcpdump -vvX
### starte netfilter
$>  cd /etc/netfilter.d 
$>  ./netfilter start
 
## mdbook
with mdbook, I can generate websites made with .md files
	
## Mehrere Fenster pro Terminal
$>  tmux 
	
$>  control + b , dann oder \% oder \grqq
### Teste Mail-Verbindung
$> telnet mail.someserver.de 25 
	
Trying 89.110.147.184... 
	
Connected to mail.someserver.de. 
	
220 v935.ncsrv.de ESMTP Exim 4.63 Tue, 01 May 2007 13:34:46 +0200 
	
HELO localhost 
	
250 mail.ploetner-it.de Hello localhost 
	
MAIL FROM: test@localhost 
	
250 OK 
	
RCPT TO: user@something.de 
	
250 Accepted 
	
DATA 
	
354 Enter message, ending with "." on a line by itself 
	
From: "Ich bin's!" <test@localhost> 
	
To: "User" < user@something.de> 
	
CC: xyz@something.de 
	
Subject: Dies ist eine Testmail 

QUIT
### Paketdetails für exim
$> apt-cache show exim

### wer braucht am meisten Speicher?
$> ncdu

### Wechsle php-Version
$>  update-alternatives --set php /usr/bin/php7.4

### Welches mail program is installed/sending emails?
$> dpkg -S `which sendmail`


# Bash
| uniq   diese pipe entfernt alle doppelten Einträge
| sort   sortiere alphabetisch
awk -F "/" '{print $1}' /path/to/file 

# Unnützes Wissen
zwei Syscalls: fork() kopiert einen Prozess, so dass das alte Programm in zwei Prozessen ausgeführt wird, und exec*() ersetzt in einem laufenden Prozess das alte Programm durch ein neues. Offensichtlich kann man die häufige Aufgabe des Startens eines neuen Programms in einem eigenen Prozess dadurch erreichen, dass erst ein Prozess kopiert und dann in der Kopie das neue Programm gestartet wird.
Damit sich Programme auf diese Weise freiwillig beenden können, brauchen sie einen Syscall. Unter Unix heißt dieser Aufruf exit().
Beim Herunterfahren des Systems wird entsprechend der Semantik beider Signale auch meist so verfahren: Zuerst wird allen Prozessen ein SIGTERM gesendet, dann einige Sekunden gewartet und schließlich allen ein SIGKILL geschickt.
