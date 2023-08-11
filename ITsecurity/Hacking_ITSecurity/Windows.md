**whoami /all** Informationen zu meinen Konto anzeigen lassen
Eine komplette Übersicht findet sich auf https://doc.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/user-rights-assignment

**LAPS- Local Admin Password Solution **
https://www.microsoft.com/en-us/download/details.aspx?id=46899

Problematisch ist die Utilman.exe und sethc.exe
Sind **Sticky-Keys** und **Erleichterte Bedienung** auf unseren Windows Servern deaktiviert?

Windows Server Security Guide
https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-security-configuration-framework/windows-security-baselines

Entfernen unsicherer Protokolle z.B.: **Samba**

Über die Registry kann ein Agreifer bei jedem Boot-Vorgang ein Skript ausführen.
Überprüfe dazu Computer\HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run

Eine Active Directory kann mit **Microsoft Advanced Threat Analytics** effektiv überwacht werden.

Security Compliance Policy verwaltet lokale Richtlinien
