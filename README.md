http://netsukuku.freaknet.org





# What is this?


Netsukuku is an alternative to the internet, It will have all of the features of the internet,
Such as websites, Instant messaging, File transfers, DNS, Etc. It functions as a
mesh network or a p2p net system that generates and sustains
itself autonomously. It is designed to handle an unlimited number of nodes
with minimal CPU and memory resources. 

Thanks to this feature it can be easily
used to build a worldwide distributed, anonymous and not controlled network,
separated from the Internet, without the support of any servers, ISPs or
authority controls.

This net is composed by computers linked physically each other, therefore it
isn't build upon any existing network. Netsukuku builds only the routes which
connects all the computers of the net.
In other words, Netsukuku replaces the level 3 of the model iso/osi with
another routing protocol.

The Domain Name System is also replaced by a decentralised and distributed
system, Being the ANDNA system. (A Netsukuku Domain Name Architecture)

The complete features list of Netsukuku is here:
http://netsukuku.freaknet.org/files/doc/misc/Ntk_features_list


In order to join to Netsukuku you have to use NetsukukuD, which is the daemon
implementing the Npv7 protocol.

Before doing anything, please read the documentation in doc/ or in
http://netsukuku.freaknet.org


# Get the code!


    $git clone git@github.com:Netsukuku/netsukuku.git 
    
    If that doesn't work, Try this!
    
    $git clone https://github.com/Netsukuku/netsukuku.git
    
    If even that doesn't work, Download the .zip from this page.


# Build and install

The dependencies of netsukuku can be gathered by running this command.

    # sudo apt-get install zlibc libgmp-dev openssl libgee-dev libpth-dev libgcrypt11-dev autoconf cmake autogen mawk gawk

To compile the code you can use scons or just go with the old school way:

    # ./configure && make && make install

But SCons is cooler:
http://www.scons.org/
(You should have installed at least the 2.4 version of Python in order to
avoid dirty bugs in scons)

You can go to the libgmp/zlib/openssl websites below if you wish, 
As they are dependenices of netsukuku. 

Here they are!

for the libgmp: http://www.swox.com/gmp/
the openssl library here: http://openssl.org
and finally the zlibs: http://zlib.net

Then go in the src/ directory and type:
    
    $ scons --help

That will show you all the options you can use in the build and installation
process. Finally execute:

    $ scons

The code will be compiled. If all went well install NetsukukuD with:

    # scons install

Now you should give a look at /etc/netsukuku.conf (or wherever you installed
it) and modify it for your needs, but generally the default options are good.

- Notes:

If you want to change some scons option to do another installation, (i.e. you
may want to reinstall it with another MANDIR path), you have to run:

    $ scons --clean


# Static Binaries and Packages

If you prefer to just install Netsukuku, without compiling it, you can
download the static binaries suitable to your platform. They come packed in
various formats (.tgz, .deb, .ipk).
The packages repository is at:
    http://netsukuku.freaknet.org/packages/ (Currently non-functional)
    
    https://launchpad.net/~michele-bini/+archive/ppa-mbxxii/+sourcepub/1032974/+listing-archive-extra
    
    (This archive contains unoffical packages, However, They have been tested, And function on Ubuntu 12.04 and earlier.)


# Kernel dependencies


(The following probably is already, If not will be soon, Unnecessary/automated.)

On Linux be sure to have the following options set in your kernel .config.
These options are taken from linux-2.6.14.
 

 Networking options

    CONFIG_PACKET=y
    CONFIG_UNIX=y
    CONFIG_INET=y
    CONFIG_IP_MULTICAST=y
    CONFIG_IP_ADVANCED_ROUTER=y
    CONFIG_IP_MULTIPLE_TABLES=y
    CONFIG_IP_ROUTE_MULTIPATH=y
    CONFIG_NET_IPIP=y
    CONFIG_NETFILTER=y

and these from linux-2.6.16.19.

 Core Netfilter Configuration

    CONFIG_NETFILTER_XT_MATCH_CONNTRACK=y
    NETFILTER_XT_TARGET_CONNMARK=y

 IP: Netfilter Configuration

    CONFIG_IP_NF_IPTABLES=y
    CONFIG_IP_NF_FILTER=y
    CONFIG_IP_NF_TARGET_REJECT=y
    CONFIG_IP_NF_NAT=y
    CONFIG_IP_NF_NAT_NEEDED=y
    CONFIG_IP_NF_TARGET_MASQUERADE=y

If you are using modules you have to load them before launching the daemon.


# How to use it


Before doing anything do:

    $ man ntkd
    $ man andna

when you feel confortable and you are ready to dare type with root
priviledges:

    # ntkd

then just wait... ^_-

(For the first times it's cool to use the -D option to see what happens).

- Note:
The daemon at startup takes the list of all the network interfaces which are
currently UP and it uses all of them to send and receive packets. If you want
to force the daemon to use specific interfaces you should use the B<-i>
option.


# Where to get in touch with us

## Mailing list

Subscribe to the netsukuku mailing to get help, be updated on the latest news
and discuss on its development.

To subscribe to the list, send a message to:
  netsukuku-subscribe@lists.dyne.org
or use the web interface:
  http://lists.dyne.org/mailman/listinfo/netsukuku
   
You can browse the archive here:
  http://lists.dyne.org/netsukuku/
  http://dir.gmane.org/gmane.network.peer-to-peer.netsukuku
 

## IRC

We live night and day in IRC, come to see us on channel
   #netsukuku
on the FreeNode irc server (irc.freenode.org).


# Bug report


{ Don't panic! }

If you encounter any bug, please report it.
Use the online bug track system:
  http://bugs.dyne.org/
or the mailing list:
  http://lists.dyne.org/netsukuku/
and explain what the problem is and if possible a way to reproduce it.


# Hack the code

Feel free to debug, patch, modify and eat the code. Then submit your results
to the mailing list ^_-

There is a lot to code too! If you are a Kung Foo coder, get on board and
help the development writing some nice poems. For a start you can take a look
at the src/TODO file.


# License and that kind of stuff...

All the Netsukuku code is released under the GPL-2, please see the COPYING
file for more information.

The authors of Netsukuku and NetsukukuD are listed in the file AUTHORS.
