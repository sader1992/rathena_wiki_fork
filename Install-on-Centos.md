This guide covers how to install rAthena on [CentOS](http://en.wikipedia.org/wiki/CentOS) and other [versions of Linux](http://en.wikipedia.org/wiki/List_of_Linux_distributions#RPM-based) that use [yum](http://en.wikipedia.org/wiki/Yellowdog_Updater,_Modified).

# Requirements
* CentOS or an RPM-based Linux that has the 'yum' command
* root access or access to an account that has [sudo privileges](http://en.wikipedia.org/wiki/Sudo)
* an Internet connection to download install packages

# Prerequisites
All of these commands will be typed at the [command-line interface](http://en.wikipedia.org/wiki/Command-line_interface).
## Install Prerequisites
* Login to your server via [SSH](http://en.wikipedia.org/wiki/Secure_Shell), or if you are already logged into a [GUI](wikipedia:http://en.wikipedia.org/wiki/Graphical_user_interface) open a terminal window.
* Unfortunately CentOS' original GCC package is outdated. It's needed to use the gcc version from the devtoolset repository to get an more up-to-date compiler:
```sh
sudo yum install centos-release-scl
sudo yum install devtoolset-7-gcc devtoolset-7-gcc-c++
```
You're able to use the gcc-7 compiler now by enabling the devtoolset:
`scl enable devtoolset-7 bash`
If you don't want to use this command every time before compiling, you can add the following to your `~/.bashrc` or `~/.bash_profile`:
`source scl_source enable devtoolset-7`
 
`sudo yum install mariadb mariadb-devel mariadb-server pcre-devel zlib-devel git`
* (Optional) type the following command to install some additional packages: 

 `yum -y install dos2unix gdb nano screen unzip wget zip`

## Create a non-root Linux user
By the [principle of least privilege](http://en.wikipedia.org/wiki/Principle_of_least_privilege), it is recommended you do **NOT** run rAthena as root. 
Type the following command to create a non-root Linux account:

`useradd --create-home --shell /bin/bash rathena4444`

`--create-home` = create the user's home directory

`--shell` = sets their login shell to [Bash](http://en.wikipedia.org/wiki/Bash_(Unix_shell))

`rathena4444` = the login name of the new Linux account

`4444` = pick your own random numbers to make the username more unique

* Set a password for the new user (run this command and follow the prompts):

`passwd rathena4444`

## Configure MySQL (MariaDB)
Note: [MariaDB](https://en.wikipedia.org/wiki/MariaDB) is a community-developed fork of the MySQL database management system. Therefore in the following section MySQL is equivalent to MariaDB and vice versa.

### Set a root password
The default MySQL Server install creates a MySQL user 'root'@'localhost' with NO password. It is recommended you create a password for the root user. 
* Run MySQL Service:

`systemctl start mariadb`
* Run this command and follow the prompts: 

`mysql_secure_installation`
* Login to your MySQL Server as root: 
* When prompted, enter your root MySQL password.

`mysql -u root -p`
* Now your prompt should look like this (the MySQL command prompt): 

### Create SQL database for rAthena
* At the MySQL prompt, type this to [create a database](http://dev.mysql.com/doc/refman/5.5/en/create-database.html) (replace `rathena4444` with the Linux username you created earlier): 

`mysql> CREATE DATABASE rathena4444_rag;`

* Create a separate database for logs: 

`mysql> CREATE DATABASE rathena4444_log;`

### Setup a MySQL user for rAthena
* At the MySQL prompt, type something like this to create a new MySQL user: 

`CREATE USER 'rathena4444'@'localhost' IDENTIFIED BY 'secretpassword';`

`rathena4444` = the name of the MySQL user (we named it the same as the Linux user to make it easier to identify)

`localhost` = the hostname or IP it will connect from

`secretpassword` = the password for this MySQL user

* [Grant privileges](http://dev.mysql.com/doc/refman/5.5/en/grant.html) to the 'rathena' MySQL user:

`mysql> GRANT SELECT,INSERT,UPDATE,DELETE ON rathena4444\_rag.* TO 'rathena4444'@'localhost';`

`mysql> GRANT SELECT,INSERT ON rathena4444\_log.* TO 'rathena4444'@'localhost';`
(note the [escaped underscore](http://dev.mysql.com/doc/refman/5.5/en/string-literals.html#character-escape-sequences))

# Install rAthena
## Login as your non-root Linux user
The rest of the setup is done as rathena4444 (the Linux user you created in step 2.2)
* Logout from root SSH (or minimize the window).
* Login to your server via SSH as the rathena4444 Linux user.

## Cloning The Repository
You can obtain the latest version of rAthena by typing the following command. This will place rAthena in a folder called rAthena, but you are free to change it to whatever you like:

`git clone https://github.com/rathena/rathena.git ~/rAthena`

## [Import](http://dev.mysql.com/doc/refman/5.5/en/batch-commands.html) MySQL Tables
* Change directory to the '''sql-files''' folder.

`cd ~/rAthena/sql-files/`

* Execute these commands (when prompted, enter your MySQL root password):

Main structure and logs (important!):
```sh
mysql -u root -p rathena4444_rag < main.sql
mysql -u root -p rathena4444_log < logs.sql
```

The following are only needed, if you want to use the item and mob sql database:
```sh
mysql -u root -p rathena4444_rag < item_db.sql
mysql -u root -p rathena4444_rag < item_db2.sql
mysql -u root -p rathena4444_rag < mob_db.sql
mysql -u root -p rathena4444_rag < mob_db2.sql
```

NOTE: if you want to use different SQL DBs for login/char/map servers this is the list of databases each server use:
* login-server: global_reg_value, ipbanlist, login, loginlog
* map-server: mapreg, item_db, item_db2, mob_db, mob_db2
* char-server: everything else + global_reg_value once again
Note that global_reg_value tables are needed by both login-server and char-server (though it may be different tables)

## Compile Source Code
```sh
cd ~/rAthena
./configure
make clean server
```

*If you're using CentOS 32-bit please use:

`./configure --disable-64bit`

### How to Recompile
In the future (after you update or edit any file in /src) to recompile: 
```sh
cd ~/rAthena
./configure # only needed when you change Makefiles
make clean # if you want to clean your current compilation
make server # rebuilds the whole server
```

# Start your rAthena Server
* Change access mode of athena-start file so that you can execute it.
* Use (dos2unix athena-start) if you are getting ^M errors, ie. newline errors 

 `chmod a+x athena-start`

* To Start

` ./athena-start start`

* To Stop

` ./athena-start stop`

* To Restart

` ./athena-start restart`

# See Also