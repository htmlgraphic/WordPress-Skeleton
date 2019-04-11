# WordPress Skeleton

Symlink your WordPress installation. This is simply a skeleton repo for a WordPress site. Use it to jump-start your WordPress site repos, or fork it and customize it to your own liking!


## Overview Guide

Having a symlinked directory can really help to update WordPress installations when new versions are released as you can host multiple WordPress sites from a single installion directory.

**How to update to the newest version of WordPress:**

```
$ git fetch origin --tags
$ git checkout <tag>
$ git checkout -b <name>
```

1. Install the newest version of WordPress using [WP Core](https://wp-cli.org/)
2.  symlink “wp” folder to the location of the WordPress files

Create the symlink as the user which will need to view any of the files. Match the owner and group which is set on other files in the directory

$ `ln -s  /home/WordPress/latest wp`

3. Create [index.php](index.php) in the root directory. Overwrite the existing file if it exists. 


---

## Troubleshooting

### Why is the wp-config.php file not found?

This is the important piece of code that need to be included in the wp-config.php file. This file is located in the directory you symlink’d to.

```
<?php include_once("${_SERVER['DOCUMENT_ROOT']}/wp-config.php"); ?>
```




### Apache Error: Symbolic link not allowed or link target not accessible

Maybe check also the permissions of the symbolic link target and be sure the apache user/group has all the needed accesses.

### Redirection issue? 
The WordPress Address (URL) should include a /wp/ at the end so you can proper login to the admin side.


### Why do I have a blank page? 
There is a blank page because the wp-content directory has not been loaded correctly. 

*Does this directory exist?*

*Database credentials?*



