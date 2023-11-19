AD stellt Informationen mit Hilfe des X.500-Protokolls zur Verfügung (LDAP)

Der DC speichert die Informationen in einer DB-Datei /C:/Windows/NTDS

Die Datenbank besteht aus verschiedenen logischen Einheiten, die Partitionen genannt werden.

Schemapartition: logische Aufbau der Objekte

Konfigurationspartition: zentrale Einstellungen, die an alle Mitglieder der Gesamtstruktur angewendet werden. Jeder Windows-Server vertraut allen Zertifikaten, die von diesem Server kommen.

Domänenpartition, speichert alle Informationen über die Objekte der Domäne.

Security Descriptor Propagator (SDProp), alle (60Minuten) werden die Admins auf definierte Werte gesetzt.

Standardrechte eines Objekts lassen sich mit adsi-edit.msc anzeigen

mit ntdsutil kann ein Snapshot vom Laufwerk gemacht werden.

Tools zum Auslesen der AD-Datanbank:
- NTDSXtract
- LibEseDB
