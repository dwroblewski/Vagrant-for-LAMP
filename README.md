Vagrant for LAMP
=============

Vagrant configured for local LAMP development. Uses an updated lucid32 box with Ubuntu 10.04.4 and VirtualBox Guest Additions 4.1.8.

Based on https://github.com/ymainier/vagrant-lamp . 

Contents
-------

The following is installed:

* VirtualBox Guest Additions 4.1.8
* emacs23-nox
* subversion
* ack-grep
* language-pack-sv
* php5-xdebug
* apache with mod_vhost_alias, mod_rewrite, mod_deflate, mod_headers, mod_php5
* php5 with apc
* mysql
* webgrind

Description
-----------
Mounts local folder with nfs for better performance. 

Thanks to dnsmasq+vhost_alias, all http requests for hosts ending with .dev are sent to /vagrant/www/$1 where $1 is replaced with the actual domain from the http header. A request to http://hellworld.dev would be sent to /vagrant/www/helloworld.dev/www . This way it's easy to setup multiple virtual hosts without a need for separate configuration for each host.

A good tutorial on how to setup dnsmasq on osx, http://davidwinter.me/articles/2011/06/18/simple-local-web-development-with-apache-and-dnsmasq/ .

Instructions
------------
1. Download and install [vagrant](http://vagrantup.com/).
2. Clone this repository.
3. Go into this repository and create box:
        cd [repo]
        vagrant up
