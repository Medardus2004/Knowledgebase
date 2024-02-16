# Authentifizierungsverfahren


## NTLM
NTLM (kurz für NT LAN Manager) ist ein Authentifizierungsverfahren für Rechnernetze. 
Es verwendet eine Challenge-Response-Authentifizierung.

Durch den Einsatz von NTLM über HTTP ist ein Single Sign-on auf Webservern oder Proxyservern unter Verwendung des Berechtigungsnachweises 
(Credentials) der Windows-Benutzeranmeldung möglich.

Eine Authentifizierung über NTLM beginnt damit, dass der Client den Benutzernamen an den Server sendet.[4] Der Server sendet daraufhin als Challenge eine Zufallszahl an den Client. Der Client sendet als Response die mit dem Hashwert des Benutzerpassworts verschlüsselte Zufallszahl zurück. Der Server verschlüsselt ebenfalls die Zufallszahl mit dem Hashwert des Benutzerpassworts, das er in seiner Datenbank oder vom Domain Controller hat, vergleicht die beiden Ergebnisse und bestätigt bei Übereinstimmung die Authentifizierung. Das Benutzerpasswort wird also nicht über das unsichere Medium gesendet.

Eine Alternative zu NTLM ist das Protokoll Kerberos, das auch unter Windows seit der Einführung des Active Directory mit Windows 2000 standardmäßig zum Einsatz kommt.[5] Wenn eine Authentifizierung mittels Kerberos nicht möglich ist, wird aber automatisch NTLM verwendet.[6] Den Port für NTLM wählt Windows in der Grundeinstellung dynamisch.[7]

Secure Password Authentication, kurz SPA, nennt Microsoft die Authentifizierung über NTLM für Microsoft Exchange Server.

## SAML
Die Security Assertion Markup Language (SAML) ist eine standardisierte Methode, externen Anwendungen und Diensten mitzuteilen, 
dass ein Benutzer derjenige ist, der er zu sein behauptet. Durch SAML wird Single-Sign-On-Technologie (SSO) möglich, denn man 
kann damit einen Benutzer einmal authentifizieren und diese Authentifizierung dann an mehrere Anwendungen übermitteln. Die neueste Version von SAML ist SAML 2.0.

Eine SAML Assertion ist eine Nachricht, mit der einem Dienst-Provider mitgeteilt wird, dass ein Benutzer angemeldet ist

SAML ist eine Technologie zur Authentifizierung von Benutzern, nicht zur Autorisierung. Das ist ein wichtiger Unterschied. 
Die Benutzerautorisierung ist ein separater Bereich in der Identitäts- und Zugriffsverwaltung.

Technologien zur Zugriffsverwaltung übernehmen die Benutzerautorisierung. Zugriffsverwaltungsplattformen verwenden 
verschiedene Autorisierungsstandards (einer davon ist OAuth), jedoch nicht SAML.
