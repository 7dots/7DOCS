# UAT (WIP)

This is a guide on how to set up a UAT site. Our UAT sites are all housed on a specific 7DOTS server for the version of PHP you need.

Below are some steps on how to create a UAT site.

1. Find the sever for the PHP version you need.
2. Create a directory for the site: `cd /var/www/vhost && mkdir new-site && cd new-site && mkdir uat`.
3. Set up the default `log` and `silverstripe-cache` directories within your site: `cd uat && mkdir log && mkdir silverstripe-cache`.
4. Add the correct permissions to these new directories: `chown -Rf apache:www-pub silverstripe-cache && chown -Rf apache:www-pub log`.
5. Add an `assets` directory and set the permissions:
   - `chown -Rf apache:www-pub assets`
   - `sudo chmod 777 assets`
6. Go to Rackspace Cloud or Cloudflare depending on the sites requirements to set up the domain (see the Domain set up page to learn how to do this).
7. Now we want to create a `vhost` for the site: `cd /etc/httpd/vhost.d` and then copy a non `ssl` file renaming it to be your new site.
8. Update the contents of the new `vhost` with the directory paths, domain etc. for your new site.
9. Test everything is okay at this point using `apachectl configtest`.
10. Add your new site to DeployHQ (see the DeployHQ page in the docs to learn how to do this).
11. Now we want to add the key to the server: `cd /home/centos/.ssh` and then `nano authorized_keys` tobe able to paste in your key after the last line.
12. Add a database to the server for the site which we can then add to the `.env` within DeployHQ config files.
13. Now we want to reload the server to make sure all our changes take effect: `sudo service httpd reload`.
14. In the route of you new site, run `certbot` and choose the number for your site to create an SSL. If all works, it should autogenerate an SSL for the site.
15. Finally, to add directory security to the site, run `htpasswd -c .htpasswd 7dots` and type in our default password.

### All done!

#### Note: This is a WIP
