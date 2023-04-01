## What are Executables

## Hacking Electron Applications

Electron is a combination of Chromium and NodeJS. 
It is vulnerable to Random Code Execution, i.e. the possilbility to execute any code on a victims computer
Electron is an open source framework to develop cross platform desktop apps

## Cross-Site Request Forgery (CSRF) Explained

iframes lets you embed one website into another, but cross iframe communication is not possible, due to same origin policy.
The policy only lets you read from the iframe if, the domain, the scheme, the port are the same.

On every single request, the cookies are automatically sent, regardless of my current domain, 
The evil page gets the cookie and can do evil stuff with this cookie.
Therefore --> sop and random cookies

