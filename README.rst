**NAME**

::

    nah - NAH


**SYNOPSIS**

::

    nah    <cmd> [key=val] [key==val]
    nahbot [-i] [-v]
    nahd 
    nahs


**DESCRIPTION**

::

    NAH has all the python3 code to program a unix cli program, such as
    disk perisistence for configuration files, event handler to
    handle the client/server connection, deferred exception handling to not
    crash on an error, a parser to parse commandline options and values, etc.

    NAH uses object programming (OP) that allows for easy json save//load
    to/from disk of objects. It provides an "clean namespace" Object class
    that only has dunder methods, so the namespace is not cluttered with
    method names. This makes storing and reading to/from json possible.

    NAH has a demo bot, it can connect to IRC, fetch and display RSS
    feeds, take todo notes, keep a shopping list and log text. You can
    also copy/paste the service file and run it under systemd for 24/7
    presence in a IRC channel.

    NAH is Public Domain.


**INSTALL**

::

    $ pipx install nah
    $ pipx ensurepath


**CONFIGURATION**


irc

::

    $ nah cfg server=<server>
    $ nah cfg channel=<channel>
    $ nah cfg nick=<nick>

sasl

::

    $ nah pwd <nsvnick> <nspass>
    $ nah cfg password=<frompwd>

rss

::

    $ nah rss <url>
    $ nah dpl <url> <item1,item2>
    $ nah rem <url>
    $ nah nme <url> <name>

opml

::

    $ nah exp
    $ nah imp <filename>


**SYSTEMD**

::

    $ nah srv > obx.service
    $ sudo mv nah.service /etc/systemd/system/
    $ sudo systemctl enable nah --now

    joins #nah on localhost


**USAGE**


without any argument the bot does nothing

::

    $ nah
    $

see list of commands

::

    $ nah cmd
    cfg,cmd,dne,dpl,err,exp,imp,log,mod,mre,nme,
    pwd,rem,req,res,rss,srv,syn,tdo,thr,upt


start a console

::

    $ nah
    >


use -v to enable verbose

::

    $ nahbot -v
    NAH since Tue Sep 17 04:10:08 2024
    > 


use -i to init modules

::

    $ nahbot -i
    >



start daemon

::

    $ nahd
    $


start service

::

   $ nahs
   <runs until ctrl-c>


**COMMANDS**

::

    here is a list of available commands

    cfg - irc configuration
    cmd - commands
    dpl - sets display items
    err - show errors
    exp - export opml (stdout)
    imp - import opml
    log - log text
    mre - display cached output
    pwd - sasl nickserv name/pass
    rem - removes a rss feed
    res - restore deleted feeds
    rss - add a feed
    srv - create service file
    syn - sync rss feeds
    tdo - add todo item
    thr - show running threads


**SOURCE**

::

    source is at https://github.com/otpcr/nah


**FILES**

::

    ~/.nah
    ~/.local/bin/nah
    ~/.local/bin/nahbot
    ~/.local/bin/nahd
    ~/.local/bin/nahs
    ~/.local/pipx/venvs/nah/*


**AUTHOR**

::

    Bart Thate <bthate@dds.nl>


**COPYRIGHT**

::

    NAH is Public Domain.
