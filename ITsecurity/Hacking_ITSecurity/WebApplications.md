Asynchrone Datenverarbeitung:
- REST
- JSON
- SOAP
- WebSockets

Alternative WebServer:
LiteSpeed, OpenResty

Session IDs sollten begrenzte Gültigkeit aufweisen

Session Fixation is an attack that permits an attacker to hijack a valid user session. The attack explores a limitation in the way the web application manages the session ID, more specifically the vulnerable web application. When authenticating a user, it doesn’t assign a new session ID, making it possible to use an existent session ID.

Ein Cross Site Angriff kann in der URL versteckt werden. Damit diese URL möglichst kurz ist nutzt man tinyurl.com oder bitly.com

Reflected-Cross-Site-Scripting bedeutet, dass JS Code direkt durch den Benutzer eingegeben wird. 
Die Ausnutzbarkeit ist aber beschränkt. Das Ziel muss einen präparierten Link klicken, der per Email versendet wird

Gefährlicher ist Stored-Cross-Site-Scripting. Dabei wird Schadsoftware auf einer Website platziert

Mit Cross Site 
