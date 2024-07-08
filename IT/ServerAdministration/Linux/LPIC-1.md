# LPIC

Die meisten
Maschinen bieten ein Konfigurationsprogramm, das beim Einschalten der Maschine ausgeführt
werden kann. Bis Mitte der 2000er Jahre war das Konfigurationsprogramm im BIOS (Basic
Input/Output System) implementiert, dem Standard für Firmware, der die grundlegenden
Konfigurationsroutinen von x86-Motherboards enthält. Ab dem Ende des ersten Jahrzehnts der
2000er Jahre begannen Maschinen, die auf der x86-Architektur basierten, das BIOS durch eine
neue Implementierung namens UEFI (Unified Extensible Firmware Interface) zu ersetzen. Diese
verfügt im Gegensatz zum BIOS über Funktionen zur Identifizierung, zum Testen, zur
Konfiguration und zu Firmware-Upgrades. Trotz der Änderung ist es nicht ungewöhnlich, das
Konfigurationsprogramm weiterhin BIOS zu nennen, da beide Implementierungen denselben
grundlegenden Zweck erfüllen

**lspci**
Zeigt alle Geräte an, die aktuell an den PCI-Bus (Peripheral Component Interconnect)
angeschlossen sind. Bei PCI-Geräten handelt es sich entweder um Komponenten, die an die
Hauptplatine angeschlossen sind (z.B. Festplatten-Controller), oder um Erweiterungskarten, die
in einen PCI-Steckplatz eingesteckt ist (z.B. eine externe Grafikkarte).

**lsusb**
Listet USB-Geräte (Universal Serial Bus) auf, die aktuell an das System angeschlossen sind.
Obwohl es USB-Geräte für fast jeden erdenklichen Zweck gibt, wird die USB-Schnittstelle meist
für den Anschluss von Eingabegeräten — Tastaturen, Zeigegeräte — und
Wechselspeichermedien verwendet.

**lsmod** 
zeigt zum Beispiel alle aktuell
geladenen Module an

Der Befehl **modprobe** dient
sowohl dem Laden als auch dem Entladen von Kernelmodulen: Zum Entladen eines Moduls und
seiner verwandten Module — solange diese nicht von einem laufenden Prozess benutzt
werden — nutzen Sie den Befehl modprobe -r

### Libraries

**ldconfig -v** zeigt alle Libraries an.
Diese sind unter /etc/ld.so.conf zu finden

es gibt dynamische und statische libraries
Eine statische Bibliothek wird zur Verknüpfungszeit mit dem Programm zusammengeführt.
Eine Kopie des Bibliothekscodes wird in das Programm eingebettet und wird Teil des
Programms haben a im Namen

dynamisch so shared object

libraries werden zuerst kompiliert und dann verlinkt

LD_LIBRARY_PATH ist für gemeinsam genutzte Bibliotheken, was PATH für
ausführbare Dateien ist.

**ldd /usr/bin/git** zeigt alle libraries.

### Debian-Paketverwaltung verwenden

**dpkg -i PACKAGENAME** installiert ein Packet.

**dpkg -r PACKAGENAME** installiert ein Packet.

**dpkg -i PACKAGENAME** Informationen über ein Packet.

**dpkg-query -S /usr/bin/unrar-nonfree** Herausfinden, welches Paket eine bestimmte Datei besitzt.

Um eine Liste aller auf dem System installierten Pakete zu erhalten, benutzen Sie die Option
--get-selections, wie in dpkg --get-selections



### Bootvorgang

Im Allgemeinen sind die Vorbereitungsschritte zum Booten eines mit BIOS ausgestatteten Systems
folgende:
1. Der POST-Prozess (Power-on Self-Test) wird ausgeführt, um einfache Hardwarefehler zu
identifizieren, sobald das Gerät eingeschaltet wird.
2. Das BIOS aktiviert die grundlegenden Komponenten zum Laden des Systems, wie
Videoausgabe, Tastatur und Speichermedien.
3. Das BIOS lädt die erste Stufe des Bootloaders aus dem MBR (die ersten 440 Bytes des ersten
Geräts, wie im BIOS-Konfigurationsprogramm definiert).
4. Die erste Stufe des Bootloaders ruft die zweite Stufe des Bootloaders auf, die für die
Präsentation von Bootoptionen und das Laden des Kernels verantwortlich ist

Wie das BIOS ist auch das **UEFI** eine Firmware, aber es kann Partitionen
identifizieren und eine Vielzahl von Dateisystemen lesen, die sich darin befinden. UEFI ist nicht
auf den MBR angewiesen und berücksichtigt nur die Einstellungen, die in ihrem nichtflüchtigen
Speicher (NVRAM) gespeichert sind, der an die Hauptplatine angeschlossen ist

Der Speicherbereich, in dem der Kernel seine Meldungen, einschließlich der Bootmeldungen,
speichert, wird als Kernel-Ringpuffer bezeichnet

Ohne Optionen zeigt der Befehl dmesg die aktuellen Meldungen des Kernel-Ringpuffer an

## Measruing
**$>  iostat**
iostat gibt eine Reihe von Werten aus und wird typischerweise mit zwei numerischen Parametern aufgerufen:
Beispiel: iostat 1 5
1 -> die Werte werden jede Sekunde erneut gemessen und ausgegeben
5 -> die Werte werden 5x ausgegeben, danach wird das Programm beendet

**$>  iotop**
Das Linux Monitoring-Tool iotop zeigt die aktuellen I/O Transferraten für die gerade laufenden Prozesse/Threads. Es verwendet dabei die I/O Usage Informationen des Linux Kernels (erfordert Linux Kernel Version 2.6.20 oder neuer).

**$>  vmstat**
Ist ein Computer zu langsam, sind die Ursachen oft nicht einfach zu ermitteln. Ist es eine zu langsame Festplatte, ist der Arbeitsspeicher zu klein oder ein überlasteter Prozessor? vmstat gibt tabellarisch Auskunft über Prozesse, Arbeitsspeicher, Auslagerung sowie Festplatten- und Prozessor-Aktivitäten. vmstat ist somit ein Hilfsmittel, um die Ursache eines Engpasses ermitteln zu können.

**$>  netstat**
erzeugt eine Anzeige, in der Netzwerkstatus und Protokollstatistiken aufgeführt werden

**$>  ss**
is used to dump socket statistics. It allows showing information similar to netstat.  It can display more TCP and  state information than other tools.

**$>  iptraf**
IPTraf ist ein konsolenbasiertes Netzwerk-Statistikprogramm für Linux. Es sammelt unter anderem Informationen über TCP-Verbindungen und zählt Pakete und Bytes

**$>  pstree, ps**
pstree steht für Process Tree. pstree stellt alle aktuell laufenden Prozesse in einer übersichtlichen Baumstruktur da.

**$>  w**
w zeigt Informationen über Benutzer an, die aktuell angemeldet sind

**$>  lsof**
steht für list open files und ist ein Hilfsprogramm, welches Informationen über geöffnete Dateien liefert. Dies hört sich im ersten Moment unspektakulär an, jedoch sollte man dabei bedenken, dass unter unixartigen Betriebssystemen, also auch (Ubuntu) Linux, alles eine Datei ist. So werden auch Blockgeräte (=Laufwerke), Netzwerkports usw. über Dateien angesprochen. D.h. lsof kann ein sehr mächtiges Tool zur Überwachung und Analyse des Systems sein.

**$>  top   htop**
zeigt eine dynamische Übersicht der laufenden Prozesse (siehe auch ps) sowie der belegten Systemressourcen an. Gegenüber dem Klassiker top bietet htop Prozessmanager jedoch einige Komfortfunktionen.

**$>  uptime**
Der Befehl uptime gibt aus, wie lange der Rechner seit dem letzten Bootvorgang läuft, wie viele Benutzer zur Zeit eingeloggt sind und die mittlere Systemauslastung der letzten Minute, 5 Minuten und 15 Minuten.

**$>  sar**
Sie können den folgenden Befehl ausführen, um die CPU-Auslastung 4 Mal alle 1 Sekunde zu überwachen.
sar 1 4

## LVM Commands
### LVM Layer 1 – Hard Drives, Partitions, and Physical Volumes
lvmdiskscan – system readout of volumes and partitions
pvdisplay – display detailed info on physical volumes
pvscan – display  disks with physical volumes
pvcreate /dev/sda1 – create a physical volume from sda1
pvchange -x n /dev/sda1 – Disallow using a disk partition
pvresize /dev/sda1 – resize sda1 PV to use all of the partition
pvresize --setphysicalvolumesize 140G /dev/sda1 – resize sda1 to 140g
pvmove /dev/sda1 – can move data out of sda1 to other PVs in VG. Note: Free  disk space equivalent to data moved is needed elsewhere.
pvremove /dev/sda1 – delete Physical volume

### LVM Layer 2 – Volume Groups
vgcreate vg1 /dev/sda1 /dev/sdb1 – create a volume group from two drives
vgextend vg1 /dev/sdb1 – add PV to the volume group
vgdisplay vg1 – Display details on a volume group
vgscan – list volume groups
vgreduce vg1 /dev/sda1 – Removes the drive from vg1
Note: use pvmove /dev/sda1 before removing the drive from vg1
vgchange – you can activate/deactive and change perameteres
vgremove vg1 – Remove volume group vg1
vgsplit and vgmerge can split and merge volume groups
vgrename– renames a volume group

### LVM Layer 3 – Logical Volumes and File Systems
lvcreate -L 10G vg1 – create a 10 GB logical volume on volume group vg1
lvchange and lvreduce are commands that typically aren’t used
lvrename– rename logical volume
lvremove – removes a logical volume
lvscan – shows  logical volumes
lvdisplay – shows details on  logical volumes
lvextend -l +100%FREE /dev/vg1/lv1– One of the most common commands used to extend logical volume lv1 that takes up ALL of the remaining free space on the volume group vg1.
resize2fs /dev/vg1/lv1 – resize the  file system to the size of the logical volume lv1.
