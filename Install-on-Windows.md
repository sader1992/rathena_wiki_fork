# Prerequisites
All of the following must be installed on your system before you proceed.
* Windows XP SP3 or later
* [Visual Studio Express 2017](https://visualstudio.microsoft.com/vs/express/)
  * For users with limited bandwidth, [follow this guide](https://rathena.org/board/topic/111269-guide-lightweight-compiler-for-windows-for-replacement-heavy-visual-studio-ide-compile-rathena-faster-save-your-bandwidth-and-disk-space/) by @annacondaqq
* [Git for Windows](https://gitforwindows.org/)
* [TortoiseGit](https://tortoisegit.org/download/)
* [MySQL Server](http://www.mysql.com/downloads/mysql/)
* [MySQL Workbench](http://www.mysql.com/downloads/workbench/)

# Obtaining the Source
## Using Git Only
**Recommended to use Git Clone because [rAthena's Github Repository](https://github.com/rathena/rathena) is up-to-date**
* Make a new folder '''rAthena''' then right-click it and choose '''Git Bash'''
* Then do <code>git clone https://github.com/rathena/rathena.git</code>
* Once it done, your local working copy is ready to use.

## Using TortoiseGit
* Right-click a folder
* Choose _TortoiseGit -> Settings_
* In _General_ put `C:\Program Files\Git\bin` (default MSysGit path) in the _Git.exe Path_
* Click OK.
* Create a new folder `rAthena` then right-click it, _Git Clone..._
* Put the URL `https://github.com/rathena/rathena`
* Click OK.
* Wait until the cloning process is done.

# Compiling

rAthena ships with solution and project files for Visual Studio from 2013 onwards.

* Open _rAthena.sln_ in your rAthena folder.
* You may need to select your desired toolset in order to compile successfully. 
* Right-click the solution node on the right side of the screen in the Solution Explorer. This should be labelled _Solution 'rAthena' (x projects)_ and select _Build solution_. If you have compiled the server before, it is recommended to use _Rebuild solution_, as it forces the compiling of all components, not just those that have changed since the last compile process.
* If the compilation was successful, the resulting executables are in the same folder as the solution named **login-server.exe**, **char-server.exe** and **map-server.exe**.


# Configuring
## IP info
Next let's get your IP info.
* Press Windows-Key + R on your keyboard.
* Type `cmd` into the box, then click OK.
Type in `ipconfig` and press the Enter key.
You should see something similar to this:
```
 Ethernet adapter Local Area Connection
    Connection-specific DNS Suffix  . :
    Link-local IPv6 Address . . . . . : 
    IPv4 Address. . . . . . . . . . . : 192.xxx.x.xx < Your IP! (LAN IP)
    Subnet Mask . . . . . . . . . . . : 255.255.255.0
    Default Gateway . . . . . . . . . : 192.xxx.x.x
```

In place of the x there will be numbers. Open notepad; go back to the console window and right-click it's window title and select option "Select..." then click and drag over your IP address (selection will appear in inverted colors), or just copy the whole thing. For Windows 7 you will need to right click the window with the text, and click mark; then click and drag. This IP address is known as your LAN IP. Next go to [http://www.whatismyip.net/ whatismyip.net] and take note of your IP address from there. This is your WAN IP, just for future reference to make it world-wide.

## Conf Folder
**Please keep in mind that if you have the intention of running rAthena on a Windows Server, you should be adding these values to the conf/import/ directory instead of changing these values**

Open char_athena.conf and map_athena.conf with your text editor of choice. If your LAN IP and WAN IP are same then put that one IP down for all of the IP locations.

### Char_athena
`login_ip` will be the LAN IP.

`char_ip` will be WAN IP. 

Change `server_name` to the name you want your server to be.

You can change `wisp_server_name` to what you would like it to be. `wisp_server_name` is the name that shows up when a character logs in and receives a PM about it being night.

The rest of things that can be changed here will be explained later.

### Map_athena
`char_ip` is the LAN IP. 

`map_ip` is the WAN IP. 

Be sure to remove the // before each IP line.

When you are done, it should look like this:
```
 // Character Server IP
 // The map server connects to the character server using this IP address.
 // NOTE: This is useful when you are running behind a firewall or are on
 // a machine with multiple interfaces.
 char_ip: 192.xxx.x.x < LAN IP
 
 // The map server listens on the interface with this IP address.
 // NOTE: This allows you to run multiple servers on multiple interfaces
 // while using the same ports for each server.
 //bind_ip: 127.0.0.1
 
 // Character Server Port
 char_port: 6121
 
 // Map Server IP
 // The IP address which clients will use to connect.
 // Set this to what your server's public IP address is.
 map_ip: 69.xxx.x.x < WAN IP
```

# Post Installation
After you have finished configuring at this point, you will need to setup the [MySQL Server](SQL_Installation) that rAthena requires.


## See Also
* [SQL Installation](Install-MySQL)
* [Git Troubleshooting](GIT_Troubleshooting)