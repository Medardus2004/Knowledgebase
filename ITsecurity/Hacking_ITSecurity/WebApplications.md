**Session Fixation** is an attack that permits an attacker to hijack a valid user session. The attack explores a limitation in the way the web application manages the session ID, more specifically the vulnerable web application. When authenticating a user, it doesn’t assign a new session ID, making it possible to use an existent session ID.

Ein Cross Site Angriff kann in der URL versteckt werden. Damit diese URL möglichst kurz ist nutzt man tinyurl.com oder bitly.com

**Reflected-Cross-Site-Scripting** bedeutet, dass JS Code direkt durch den Benutzer eingegeben wird. 
Die Ausnutzbarkeit ist aber beschränkt. Das Ziel muss einen präparierten Link klicken, der per Email versendet wird

Gefährlicher ist **Stored-Cross-Site-Scripting**. Dabei wird Schadsoftware auf einer Website platziert
XSS bietet auch die die Möglichkeit der Infizierung von Webbrowsern. Eine komfortable Möglichkeit bietet hier das BEEF-Framework.
Der Angreifer muss dazu einen BEEF-Server betreiben, der über das Internet erreichbar ist.
Dabei wird eine JavaScript Datei eingeschleust, dies führt zu einer ständigen Kommunikation zwischen Client und Server.
Ständiges Polling für neue Aufträge des BEEF-Servers 

https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html

**DOM-based XSS** entsteht, wenn Benutzereingaben ungefiltert in die Generierung von dynamischen Inhalten im jS des Browsers übernommen werden.
Die injizierten Daten werden dann in Sinks ausgeführt

**Cross Site Request Forgery** Der Admin ist eingeloggt und erhält einen Link, in dem z.B.: ein neuer User angelegt wird.
Abhilfe schafft der CSRF Token. Dieser Token ist nur für die nächste Anfrage des Webclients an den Server gültig.

**Directory Traversal** versteht man eine Methode, Dateien außerhalb des Webserver-Root-Verzeichnisses zu erreichen.
Die Filterung der Zeichenkombination ../ hilft nur wenig, wenn man kann die Eingabe zB durch doppeltes Encoding %252 oder UTF8 %cO%ae verschleiern.

**Local File Inclusion**, gelingt es einem Angreifer über Directory Traversal, Code zu lesen, so könnte auch das Ausführen von Code möglich sein.
Zuerst wird eine nicht vorhandene Datei (mit PHP-Source Code) aufgerufen. Dies wird ins Log geschrieben. 
Durch DT kann der Angreifer nun versuchen, diesen SC im aufzurufen

**Remote File Inclusion**, ist nur möglich, wenn der Webserver erlaubt, fremde URLs zu inkludieren

**File Upload**, erlaubt eine Website, Files hochzuladen, so kann dies ausgenutzt werden, um Schadsoftware hochzuladen.

**sqlmap** erlaubt eine automatische Suche nach SQL-Injection-Verwundbarkeiten.

**Blind-SQL-Injection** durch trial and error kann aus eine Datenbank ausgelesen werden, ob z.B: ein User exisiert (boolean). Auch kann man aus der Antwortzeit vermuten, ob eine Datenbankabfrage true oder false zurückgibt. Man kann so ganze Passwörter erraten

**Advanced SQL-Injection: Out of Band Data Exfiltration**: versuchen Daten über einen Out-of-Band Kanal zu extrahieren

**Advanced SQL-Injection: Error based SQL-Injection**: wenn eine SQL-Injection in der Lage ist, Fehler zu erzeugen, dann kann man damit auch Daten auslesen.

**Comand Injection** Ein Angreifer kann versuchen, die Funktion in einem Eingabefeld zu. Comand Injection Angriffe lassen sich durch Commix leicht automatisieren.

**Click Jacking** ist eine Technik, in der 2 Webseiten überlagert dargestellt werden.

**XML-Angriffe**, zB XML-Bomben. Lassen sich mit XPath Bruter automatisieren. https://github.com/lanmaster53/recon-ng

**Server Side Request Forgery** bringt ein Angreifer ein System dazu, Requests an andere Systeme abzusetzen.

**Angular Template Injection** manche Versionen von Angular sind anfällig für Template-Injection Attacken. Mehr dazu https://gist.github.com/jeremybuis

**Angriffe auf Objekt-Serialisierung**, unter Umständen lässt sich der Deserialisierungsvorgang so manipulieren, dass am Zielsystem injizierter Code ausgeführt wird. https://github.com/frohoff/ysoserial

**Schwachstellen im CMS** Wordpress lässt sich mit wpscan untersuchen.
https://github.com/whoot/Typo3Scan

# Testmaterial
https://vulnhub.com/
https://www.exploit-db.com/


