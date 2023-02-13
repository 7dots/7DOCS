# Directory Security

How to add directory security to restrict access to a domain. Typically used for UAT or staging sites shared with the client.

```bash
# Navigate to vhosts directory
cd /etc/httpd/vhost.d

# Open vhost file
nano my-site-le-ssl.conf
ctrl + x to save file

# Add the following inside the <Directory> tag
AuthType Basic
AuthName "Authentication Required"
AuthUserFile "/var/www/vhosts/my-site/.htpasswd"
Require valid-user

# Generate encrypted password from https://wtools.io/generate-htpasswd-online
User: 7dots
Password: cellfour

# Navigate to restricted directory defined in the vhost
cd /var/www/vhosts/my-site

# Open .htpasswd file
nano .htpasswd

# Paste in user and encrypted password
7dots:$apr1$r8nkgm2s$RQNli4UlCtx89ZoiGfjgb.
ctrl + x to save file

```
