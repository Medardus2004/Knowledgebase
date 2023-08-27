## Post-Mortem

Unter Kali Linux

**deaktiviere das automatische Einbinden** neu erkannter Laufwerk: systemctl stop udisks2.service

**Kernelmeldungung:** dmesg

**Übersicht der Laufwerke:** fdisk -l

**Eins zu eins Kopie**: dd oder dc3dd

**Wiederherstellung von Dateien:** foremost

**Untersuchung Zeitstempel:** stat

**Auslesen von Metadaten:** mat, exiftool

Sehr mächtiges Tool: **Autopsy**


## Live-Analyse

**Informationen gewinnen:** buld-extractor -o output Narcos-Mem-2.001

**Tool zum Passwort knacken:** hashcat

**Tool zum Austesten einer Liste von AES-Schlüsseln:** github.com/AmNe5iA/MKDecrypt

