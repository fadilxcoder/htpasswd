# Notes

- https://hostingcanada.org/htpasswd-generator/
- Username : `fadilxcoder`
- Password : `u99qDU2BVgBgD@i`
- Mode : **Apache specific salted MD5 (insecure but common)**
- Apache virtual host setting

```
<VirtualHost *:80>
	ServerName api.platform.local
	DocumentRoot c:/wamp64/www/api-plateform-symfony/public/
	<Directory "c:/wamp64/www/api-plateform-symfony/public/">
		SetEnvIfNoCase HOST ^api\.platform\.local\.?(:80)?$ PROTECTED_HOST
		AuthUserFile c:/wamp64/www/.htpasswd
		AuthType Basic
		AuthName "Password Protected"
		Order Deny,Allow
		Satisfy any
		Deny from all
		Require valid-user
		Allow from env=!PROTECTED_HOST
  </Directory>
</VirtualHost>
```
