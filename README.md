The ability to create and utilize tools, makes human race dominant in world. Tools make our work easier and also saves time. One of the tools, I am going to share is bash shell script to create apache2 server virtual host.
Why Virtual Host?

Using virtual host we can run more than one web site (such as dev.drupal-cms.com, stage.drupal-cms.com and www.drupal-cms.com) on a single machine. It can be "IP-based" or “name-based”. In IP-based you can have different IP address for each web site. In name-based you can have multiple names running on each IP address.
Shell script code
Explanation

Script expects 3 strings as input:

    Domain name: Name of domain you wish to give for the site. Eg: drupal-cms.local or stage.drupal-cms.com or drupal-cms
    Full path to webroot: Full path to site webroot. Eg: /var/www/html/drupal-cms
    Server admin (optional): Site server admin email id. This is optional, default value will be ‘webmaster@localhost’

Script does the following to create a virtual host for apache2:

    Creates virtual host rules files inside `/etc/apache2/sites-available/` (line number 12 to 24)
    Creates an IP address mapping in ‘/etc/hosts’ file. Mapping would be like this 127.0.0.1 $name (line number 26)
    Enables the site, a2ensite $name
    Restarts apache2 server, service apache2 reload

Usage

    Download or clone the script from https://github.com/manoj-apare/Virtual-Host-Script
    Make it executable.
    Run the command: sudo [path-to-script]/virtual-host-script.sh [domain-name] [full-path-to-webroot] [optional-server-admin-email-id]


Note: third argument is optional.
CLI


That’s it. Now you can access the site using newly created virtual host by clicking the link printed by the script on CLI.	
