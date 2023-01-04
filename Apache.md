
# Apache
	
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
	
### Php benutzen
 <FilesMatch \.php\$>
	
                SetHandler "proxy:unix:/run/php/php7.4-fpm.sock|fcgi://localhost"
	
        </FilesMatch> 
	        
### Erlaube nur bestimme Abfrage-Methoden
	Header set Access-Control-Allow-Methods "POST, DELETE, OPTIONS" 
	
                ProxyPass https://dev.mv.app.medi.de/api/eshop/patient 
	
		$> a2enmod allowmethods
	
### php7.4 via vhost zur Verfügung stellen

wget https://mirrors.edge.kernel.org/ubuntu/pool/multiverse/liba/libapache-mod-fastcgi/libapache2-mod-fastcgi_2.4.7~0910052141-1.2_amd64.deb
	
dpkg -i libapache2-mod-fastcgi_2.4.7~0910052141-1.2_amd64.deb
	
a2enmod fastcgi actions
	
apt -y install php7.4-fpm php7.4-bcmath php7.4-curl php7.4-gd php7.4-mbstring php7.4-mysql php7.4-xml php7.4-zip
	
vi example.conf

<IfModule mod_fastcgi.c>

       AddHandler php74-fcgi-stage.medi-brandwebsite.wtf .php
	
       Action php74-fcgi-stage.medi-brandwebsite.wtf /php74-fcgi-stage.medi-brandwebsite.wtf
	
       Alias /php74-fcgi-stage.medi-brandwebsite.wtf /usr/lib/cgi-bin/php74-fcgi-stage.medi-brandwebsite.wtf
	
       FastCgiExternalServer /usr/lib/cgi-bin/php74-fcgi-stage.medi-brandwebsite.wtf -socket /run/php/php7.4-fpm.sock -idle-timeout 1800 -pass-header Authorization
	
       <Directory "/usr/lib/cgi-bin">
	
               Require all granted
	
       </Directory>
	
</IfModule>

*Innerhalb VirtualHost*



	
  
	<IfModule mod_fastcgi.c>
	
               <FilesMatch ".+\.ph(p[345]?|t|tml)$">
	
                       SetHandler php74-fcgi-stage.medi-brandwebsite.wtf
	
               </FilesMatch>
	
       </IfModule>
	
	
	
	### Wichtige Header 

*Security.conf*
	

Setting this header will prevent MSIE from interpreting files as something else than declared by the content type in the HTTP headers. Requires mod_headers to be enabled.
	
Header set X-Content-Type-Options: "nosniff"

Setting this header will prevent other sites from embedding pages from this site as frames. This defends against clickjacking attacks.Requires mod_headers to be enabled.

Header set X-Frame-Options: "sameorigin"


target website is being served from HTTPS only

Header always set Strict-Transport-Security "max-age=31536000; includeSubDomains"

