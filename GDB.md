---
title: GDB
permalink: /GDB/
---

GDB stands for GNU DeBugger. It is a program for \*nix related systems that allows you to view stacktrace and coredumps of your servers if/when they crash.

Getting GDB
===========

Typically GDB comes installed on most \*nix distro's. It comes installed on FreeBSD 7.1-RELEASE or newer if the ports collection is installed. Typically, it will be located in /usr/bin/gdb, but if it is not, you can either compile it from source or install it using your package manager for your distribution.

Debian Based (apt-get, aptitude or synaptic)
--------------------------------------------

On Debian based systems, you can use apt-get or aptitude, or the synaptic package manager to install gdb. If you prefer the terminal, you can issue ONE of the following to install gdb:

`[sudo] aptitude install gdb`
`[sudo] apt-get install gdb`

If you have access to gdm and the synaptic package manager, you can simply search for 'gdb' and mark for complete installation.

YUM based (Redhat systems)
--------------------------

On YUM based systems, you can simply issue the following to install gdb via RPM packages:

`yum install gdb`

\*BSD based
-----------

Typically GDM will come with an install of FreeBSD, but if it's not, it is best to make it from source, skip ahead.

Compiling from source
---------------------

Use your favourite download manager (wget, etc) to get the .tar.gz of the latest stable version of gdb from gdb's website. (http://www.gnu.org/software/gdb/)

Extract the .tar.gz using the following command:

`tar -zxf gdb-x.xx.tar.gz`

You need a GCC compatible compiler, so if you don't have one, get one now. there is a 99% chance that your distribution comes with a gcc compiler.

`./configure && make && make install`

Should install it for use. If you're on a \*BSD based system, you may have to issue the following command to be able to use it.

`% rehash`

Using gdb with rAthena
======================

Start rathena with gdb
----------------------
When you can reproduce a crash, it's often useful to directly start rAthena from gdb.
In this example we'll start the map-server in gdb:

`gdb map-server`

To actually run it, we type `r` in gdb:

`gdb> r`

The map server starts and we can reproduce the crash. After the crash we can just enter `bt full` to see the full stack during the crash.

`gdb> bt full`


Generating a core file
----------------------
First you need to set the size of core dumps to unlimited. For the current session you can type:

`ulimit -c unlimited`

Or to make this setting permanent edit `/etc/security/limits.conf` and uncomment `* soft core unlimited`.
(Needs a reboot)

Then you just need to reconfigure your rathena with the gdb option enabled:

`./configure --enable-debug=gdb`

And recompile rathena. The next time the server crashes, it should generate a core file.

Viewing the core file
---------------------
Find out which program(map/char/login server) crashed and it's core file (should be named the same as the server file with an additional ".core" extension).. then on the console, type:

`gdb xxx-server xxx-server_sql.core`

If a valid dump was found, you should get a prompt

`gdb>`

At that prompt, type:

`gdb> bt full`

And that will give you a full output of the problem area and a line number in which you should look for the crash. This just told you where the crash is located and what line you should look at to fix it. If you feel that is a development problem, feel free to submit a bug with that full report and one of the core developers can look into it.

See Also
--------

-   [Original guide to Core/Stack dumps](http://www.eathena.ws/board/index.php?showtopic=91817) by ViciousPucca
-   [Download page for GDB](http://www.gnu.org/software/gdb/download/)
-   [GDB Errors](https://stackoverflow.com/questions/7732983/core-dump-file-is-not-generated)

[Category:Debugging](/Category:Debugging "wikilink")