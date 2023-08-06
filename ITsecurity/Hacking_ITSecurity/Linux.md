## Linux

** More information 

https://madaidans-insecurities.github.io/guides/linux-hardening.html
http://ubuntu.com/server/docs/security-introduction
https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/9

Sicherheitsreformen
Trennung zwischen System und Nutzerdaten

Disable IPv6 in /etc/sysctl.conf
Auch müssen Konfigurationsanweisungen auf /etc/netplan entfernt werden

Die Datei /var/run/reboot-required weist auf die Notwendigkeit eines Reboots hin

package-info unter ubuntu-support-status

Mehr Infos 
https://kofler.info/die-lts-frage/
https://usn.ubuntu.com/usn
https://people.canonical.com/~ubuntu-security/cve/main.html

Stärkeres Passwort und Verstärkung htaccess

Wenn ein Packet verdächtig erscheint, kann 
$> dpkg -S /path/to/file 
das package feststellen

Alle aktiven Verbindungen auflisten
$> netstat -tupen

Informationen über Programm das auf Port 143 läuft
$> lsof -RPni :143

Mehr Informationen über den Prozess anhand der Prozessnummer
&> lsof -p 2065
