sitemigrate
===========

Full Site Migration for Drupal 6 or 7 Multi-site from Remote Server

Contributor:  Diana Woodhouse, UNC Chapel Hill, Student Affairs IT
Requires:  Drupal 6 or 7 multi-site instance, drush for V7, bash, PHP

Description
===========
Download the 'sitemigrate' folder to /usr/local/bin

Edit /etc/profile and update the path to include the path
PATH=/usr/local/bin/sitemigrate:$PATH

The command is 'sitemig' and it must be run in the drupal multi-site docroot.  It is used to migrate a remote site within a multi-site instance.

Before 'sitemig' is used, run rsync to synchronize the remote environment with the local environment.  For example,

rsync -rp root@remotesite.abc.xyz.com:/WebServer/Documents/Library/drupaldocroot .
<enter root passwd>

Multi-site instances of Drupal 6 or 7 needs site migration functionality for moving sites from development to production.

Since sites in multi-site instances have fixed paths based on the site folder name, it is important to convert all instances of the path in the database and the filesystem.

Many of the fields in the Drupal tables are serialized data, so the migration tool performs unserialized commands on the tables and then string replaces the old domain (source) to the new domain (target).  



Instructions
============
Recommended location
/usr/local/bin/sitemigrate


