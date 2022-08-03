# Linux

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

### Erzeuge htaccess
	
$> htpasswd -c -B .htusers someuser
	
*apache-config*
	
 <Location /api/bi/ >
	
                Order deny,allow 
	
                Allow from all 
	
                AuthType Basic 
	
                AuthName "Password required"
	
                AuthUserFile /var/.htpasswd.d/.htusers  
	
                <RequireAny> 
	
                        Require valid-user 
	
                </RequireAny> 
	
        </Location> 
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
### Apache in php benutzen
 <FilesMatch \.php\$>
	
                SetHandler "proxy:unix:/run/php/php7.4-fpm.sock|fcgi://localhost"
	
        </FilesMatch> 
        
### Erlaube nur bestimme Abfrage-Methoden
	Header set Access-Control-Allow-Methods "POST, DELETE, OPTIONS" 
	
                ProxyPass https://dev.mv.app.medi.de/api/eshop/patient 
	
		$> a2enmod allowmethods
	
### Colorscheme im vim-Editor ändern
$> echo "colorscheme desert" >> /root/.vimrc

### TSM-Mobaxterm
starte mobaexterm und klicke auf "X server" 
	
/opt/tivoli/tsm/client/ba/bin
	
$> export DISPLAY=private\_IP\_eigner\_Rechner:0.0 
$> ./dsmj oder ./dsmc
	
### Zeige offene Ports
$> ss -ltn 

### Neuen Nameserver auf Server hinterlegen
$> echo "nameserver 8.8.8.8" | sudo tee /etc/resolv.conf > /dev/null
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
 
# IT-Security
### Herausfinden ob man gehackt wurde
commands www  and  who  may not show users logged from pseudo terminals like Xfce terminal or MATE terminal. 
	
Was der user gemacht hat steht in /home/user/.bash\_history 
	
$> lsof  -p 
	
$> netstat -la 
	
$> iftop -i <interface> 
	
$> chkrootkit

# Azure
### Cloudidentitäten 
Diese Benutzer existieren nur in Azure AD. Dabei kann es sich z. B. um Administratorkonten oder von Ihnen selbst verwaltete Benutzer handeln. Cloudidentitäten können sich in Azure Active Directory oder einer externen Azure Active Directory-Instanz befinden, wenn der Benutzer in einer anderen Azure AD-Instanz definiert ist. Diese Konten werden gelöscht, wenn sie aus dem primären Verzeichnis entfernt werden. 
### Mit dem Verzeichnis synchronisierte Identitäten
Diese Benutzer befinden sich in einem lokalen Active Directory. Sie gelangen über eine Synchronisierung mit Azure AD Connect zu Azure. Ihre Quelle lautet Windows Server AD.
### Gastbenutzer
Diese Benutzer befinden sich außerhalb von Azure. Dabei kann es sich z. B. um Konten anderer Cloudanbieter oder um Microsoft-Konten wie etwa Xbox Live handeln. Ihre Quelle lautet Eingeladener Benutzer. Diese Art von Konto eignet sich für externe Anbieter oder Auftragnehmer, die Zugriff auf Ihre Azure-Ressourcen benötigen. Sobald deren Mitwirkung nicht mehr erforderlich ist, können Sie das Konto und den gesamten Zugriff entfernen.

### Sicherheitsgruppen
Sicherheitsgruppen werden zum Verwalten des Mitglieder- und Computerzugriffs auf freigegebene Ressourcen für eine Benutzergruppe verwendet. Beispielsweise können Sie eine Sicherheitsgruppe für eine bestimmte Sicherheitsrichtlinie erstellen. Auf diese Weise können Sie allen Mitgliedern gleichzeitig mehrere Berechtigungen erteilen, anstatt diese jedem Mitglied einzeln hinzufügen zu müssen. Für diese Option ist die Rolle eines Azure AD-Administrators erforderlich.
### Microsoft 365-Gruppen
Microsoft 365-Gruppen bieten eine Möglichkeit für die Zusammenarbeit, indem Mitgliedern beispielsweise der Zugriff auf freigegebene Postfächer, Kalender, Dateien und SharePoint-Websites gewährt wird. Sie können Personen außerhalb Ihrer Organisation Zugriff auf die Gruppe gewähren. Sowohl Benutzer als auch Administratoren können Microsoft 365-Gruppen verwenden.

### App Insights
Application Insights is a feature of Azure Monitor that provides extensible application performance management (APM) and monitoring for live web apps. Developers and DevOps professionals can use Application Insights to
