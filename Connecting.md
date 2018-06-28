This article covers taking the configuration steps to ensure a successful connection to your servers. You are required to know the in and outs of your OS, as well as what a [LAN IP](/wikipedia:Local_area_network "wikilink") and a [WAN IP](/wikipedia:Wide_area_network "wikilink") are.

Basics of the three servers
---------------------------

### Login Server

The login server handles all login packets from the client. The client sees the login server first and connects to it first. The login server listens on the port 6900 by default and usually reads data from the login table. The login server connects directly to the character server and passes it's information to it once the client has successfully logged in. If your login server won't connect, your players cannot login in, but can play.

Config file: [conf/login_athena.conf](https://github.com/rathena/rathena/blob/master/conf/login_athena.conf)

### Character Server

The character server handles all character selection and character loading for the map server. The character server receives commands to primarily display characters once the client has logged in. The character server listens on the port 6121 by default. It also handles the loading and saving of most character data. If the character server becomes disconnected, character data saving is not possible.

Config file: [conf/char_athena.conf](https://github.com/rathena/rathena/blob/master/conf/char_athena.conf)

### Map Server

The map server handles all map functions, including, but not limited to, mob functions, map functions, NPC loading and unloading, as well as NPC processing. the map server is your bread and butter and allows people to play on your server. It listens on the port 5121 by default.

If the character server becomes disconnected from your map server, it's likely the mapserver will disconnect everyone from it. This is not the case when the MySQL server loses its connection to rAthena, as rAthena currently does not restore this connection.

Config file: [conf/map_athena.conf](https://github.com/rathena/rathena/blob/master/conf/map_athena.conf)

Configuring rAthena for use
---------------------------

After you have finished [compiling](/compiling "wikilink") rAthena, you can set it up for use. There will be four files that we will concentrate on. Any settings we change in these files should **always** be moved to the relevant import folder files. If your compiler hasn't already made a copy of the folder and named it /trunk/conf/import do that now.

### Using the /conf/import/ folder

This folder In this folder, you can 'import' your settings into each of the respected files. All you need is each parameter. When you do this, your settings will never be overwritten when you need to update your rAthena, as the import folder is built once. You can throw all of your settings in here and they will remain as they are, and will read AFTER the main settings, which means these settings will take priority.

### Step 1. Interserver Communication Passwords

First, you will need to set an intercommunication password and user. This is one of the most important steps to securing your server.

In order for the char-server to accept commands and packets from the login server, and for the map-server to accept commands and packets from the char-server they have to 'log-in' to each other, using the Server Communication passwords. You MUST set these to something other than defaults, but you can set them to random characters, as long as they are the same in the three places they appear in, which are: , and your login sql table. They are defaulted to s1/p1, and **MUST** be changed.

Changes must be made to the import folder to ensure proper upgradability. A good habit to get into when working with SVN. Simply copy and paste the lines you wish to alter from the .conf file to the relevant .txt file in the import folder. Your `/conf/import/char_athena.txt` and `/conf/import/map_athena.txt` files should look as follows, with *no* changes made to or :
````
    // Server Communication username and password.
    userid: [new user]
    passwd: [new password]
````

The `login` table should match. Use this SQL query (or make the changes using your favourite SQL gui):
````sql
    UPDATE login
    use databasename_rag;
    set `userid` = "[new user]", `user_pass` = "[new password]" where `account_id` = 1;
````

For those of us that aren't so familiar with mysql (don't you just love these tutorials?)

````sql
    UPDATE databasename.login SET `userid` = 'MyInterServerUser',
    `user_pass` = 'MyInterServerPassword' WHERE `account_id` = 1;
````

**Note**: It should all be on one line. Entering the relevant parameters where needed.

After the user and password is set, you can move on down the page.

### Step 2. [Login Server](https://github.com/rathena/rathena/blob/master/conf/login_athena.conf)

Usually there is nothing to be done here in terms on connection. You may want to edit your `login_port` to something other than default, but it must be an unused port by your OS.

You can find this out by starting all the services that you need on the server and issuing the following commands to your console:

**If using Windows:**
Goto Start, then click 'Run'. Type 'cmd' and press enter. Run the following command:
````
    netstat -a
````
**If using \*nix:**
````
    $ lsof -i
````

Once you have selected a port if you're going to change it, your `conf/import/login_athena.txt` file should look as follows, with *no* changes made to (again just copy pasting the lines we want to change from one file to the other):
````
    // Login Server Port
    login_port: [new port]
````

### Step 3. [Char Server](https://github.com/rathena/rathena/blob/master/conf/char_athena.conf)

Tis config file for the char-server to read. When you open this up, there are a few things we need to do in here.

Firstly we should name our server:

When setting server_name, be sure to not use spaces as it says.
````
    // Server name, use alternative character such as ASCII 160 for spaces.
    // NOTE: Do not use spaces in the name, or guild emblems won't work client-side!
    server_name: [new server name]
````

````
    // Wisp name for server: used to send wisp from server to players (between 4 to 23 characters)
    wisp_server_name: [new server name]
````

Usually, rAthena will auto-detect your external and internal IP if the IP fields are [commented out](comments), but let's go ahead and remove the two slashes (`//`) from login_ip and char_ip.

The login_ip will point to the IP address where the login server will be running. Usually this is the localhost, or 127.0.0.1. If the login-server is to be located on the same network as the char-server (but on a different PC), use the LAN IP of the login server's machine. If you are running a dedicated machine in a datacenter, or you know your IP is not going to change, you can set this to your WAN IP.

````
    // Login Server IP
    // The character server connects to the login server using this IP address.
    // NOTE: This is useful when you are running behind a firewall or are on
    // a machine with multiple interfaces.
    login_ip: [new ip here]
````

The char_ip parameter will **ALWAYS** be your WAN IP, no exceptions. This is the IP that the char-server will accept connections with.

````
    // Character Server IP
    // The IP address which clients will use to connect.
    // Set this to what your server's public IP address is.
    char_ip: [your wan ip here]
````

If you changed the login_port in login_athena.conf, this setting here will need to match it.
````
    // Login Server Port
    login_port: [new port]
````

Make sure to make any changes in the import folder as always.

### Step 4. [Map Server](https://github.com/rathena/rathena/blob/master/conf/map_athena.conf)

This file sets parameters for the map-server to read.

The char_ip will point to the IP address where the login server will be running. Usually this is the localhost, or 127.0.0.1. If the char-server is to be located on the same network as the map-server (but on a different PC), use the LAN IP of the char server's machine. If you are running a dedicated machine in a datacenter, or you know your IP is not going to change, you can set this to your WAN IP.

````
    // Character Server IP
    // The map server connects to the character server using this IP address.
    // NOTE: This is useful when you are running behind a firewall or are on
    // a machine with multiple interfaces.
    char_ip: [new ip here]
````

The map_ip parameter will **ALWAYS** be your WAN IP, no exceptions. This is the IP that the map-server will accept connections with.

````
    // Map Server IP
    // The IP address which clients will use to connect.
    // Set this to what your server's public IP address is.
    map_ip: [your wan ip here]
````

Make sure to make any changes in the import folder as always.

### Step 5. [Inter Server](https://github.com/rathena/rathena/blob/master/conf/inter_athena.conf)

This config related how login, char, and map server connect to your ragnarok database(s). The parameters for database connection will have pattern as the list below, which `[server]` is login, ipban, char, and map
* [server]_server_ip: 127.0.0.1
* [server]_server_port: 3306
* [server]_server_id: ragnarok
* [server]_server_pw: ragnarok
* [server]_server_db: ragnarok

You have to change those config to connect your database
* `server_ip` is the IP of the MySQL/MariaDB server.
* `server_port` is port of MySQL/MariaDB's port
* `server_id` is the username you use to login. For security, this should **NEVER** be root!
* `server_pw` is the password that the user will login with.
* `server_db` is set to whatever the database name will be. Usually, this is just 'ragnarok'.

**NOTES:** (must [recompile your server](Install-on-Windows) after changing)

-   \[Hostname\] If you prefer to use name of hostname than the IP and the hostname length is more than 63 characters, you must change the max length on <em>/src/login/account.cpp</em>

        char   db_hostname[64];

    to

        char db_hostname[YOUR_HOSTNAME_LENGTH];

    ([bugreport:8003](http://rathena.org/board/tracker/issue-8003-31-characters-is-not-long-enough-for-hostnames/))


Starting rAthena
----------------

When you're all done configuring rAthena, you can start it up. You can do this by simply running each of the three servers (the .bat files will be created for Windows on compilation success, or athena-start.

Client Side
-----------

### Diff your client

See [Hexing](/Hexing#Creating_custom_RagRE_client_using_a_DIFF_patcher "wikilink").

### Data Folder

1.  Download the most recent data folder [here](http://svn6.assembla.com/svn/ClientSide/).
2.  Edit your [clientinfo.xml](/Clientinfo "wikilink") as needed.

### Connect

Execute your exe.

Trouble Shooting
----------------

Its always best to post in the [client support](http://rathena.org/board/forum/98-client-side/) sub-forum for things that go wrong with the client, and [server support](http://rathena.org/board/forum/23-rathena-server-support/) sub-forum for things that go wrong with rAthena connecting or if errors pop up in your server log.

### Packet Version
Before running your server, by default rAthena using 2015-11-04. If you want to change to other kRO client make sure you change the `PACKETVER` definition in your server too.
1. Open [src/custom/defines_pre.hpp](https://github.com/rathena/rathena/blob/master/src/custom/defines_pre.hpp)
2. Add a new entry for your PACKETVER, as example if you are using RagexeRE 2017-09-20b
3. After make a changes, you have to recompile login, char, and map server
````cpp
// Copyright (c) rAthena Dev Teams - Licensed under GNU GPL
// For more information, see LICENCE in the main folder

#ifndef _CONFIG_CUSTOM_DEFINES_PRE_HPP_
#define _CONFIG_CUSTOM_DEFINES_PRE_HPP_

/**
 * rAthena configuration file (http://rathena.org)
 * For detailed guidance on these check http://rathena.org/wiki/SRC/config/
 **/

#define PACKETVER 20170920

#endif // _CONFIG_CUSTOM_DEFINES_PRE_HPP_
````

[Category:Configuration](/Category:Configuration "wikilink")