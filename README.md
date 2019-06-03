# Vagrant for Magento 2 developing
This vagrant box with environment optimized for Magento 2 developing.
Including:
 - Ubuntu18.04, 
 - PHP7.2,
 - MariaDB 10.3.15,
 - XDebug 2.6.0

 
 ## HOW TO USE
 Change configs in _vagrant/config.yaml_ file:
 - hostname
 - private_ip
 
 Type next commands in vagrant/ directory:
 - `vagrant plugin install vagrant-hostmanager` (if didn't installed)
 - `vagrant plugin install vagrant-disksize` (if didn't installed)
 - `vagrant up`
 
 ## Vagrant machine configurations
 You can configurate you machine in _config.yaml_ file.
 
 Allowed configs:
  - **hostname**
  
  set here your project host name, so you will can use http://vagrant.sample instead *private_ip* to access website
  for using this need to install host manager plugin for vagrant - `vagrant plugin install vagrant-hostmanager`
  - **private_ip**
  
  IP address of you project website, you will access to website by this IP address in browser 
  - **use_nfs**
  
  0/1 values, will use or not network file system, strongly reccomend to enable for better permormance
  - **disk_size**
  
  Max disk size of your future machine. Default value 60GB.
  - **memory_size**
  
  Memory allowed to your future machine. Default value 512MB.
  
  ## Directories
  
  Your project will locate in html directory. On vagrant machine projet locate in /var/www/html/ directory.
  
  Syncing directories ../html -> /var/www/html
  
  ## How to login into vargant machine:
  First way - using vagrant command
  
  `vagrant ssh`
  
  Second way - login through ssh
  
  `ssh vagrant@127.0.0.1`
 
 ## Credentials
  
 ### SSH
 
 username - **vagrant**
 
 password - **vagrant**
 
 
 ### MySQL

 username - **root**
 
 password - **root**

 ### Login as root user
 For login as _root_ user next command:
 
 `sudo su`
 
 ### Login as www-data user
 For login as _www-data_ user next command:
 
 `sudo su -l www-data -s /bin/bash`
 
 ### XDebug enabling
 To enable the XDebug, uncomment the **;zend_extension=/usr/lib/php/20170718/xdebug.so** line
 in the **/etc/php/7.2/mods-available/xdebug.ini**

