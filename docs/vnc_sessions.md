# Instrument VNC Sessions

## Introduction

Keck instruments are controlled through VNC sessions.  These sessions are desktops which exist on the VNC server which is *not* the instrument server.  The VNC servers provides the windowing environment, but may or may not run any actual GUIs or keyword services for the instruments.  Some GUIS may be brought up and displayed through ssh (i.e. using `ssh -X`).

Prior to 2018, all Keck instrument VNC desktops were served from one of two SunOS machines (`svncserver1` and `svncserver2`).  Since then many instrument have transitioned to having their own linux based VNC server.  The instrumeent specific VNC server is typically named with the instrument name (i.e. `mosfire`), however there are aliases to vm-instrumentname (i.e. `vm-mosfire`) as these were created as virtual machines and their network names were chosen to reflect that.

## kvncstatus

There is a command on each VNC server called `kvncstatus` which will list all of the VNC sessions currently running on that server.  To only get the VNC sessions running for the current user, run `kvncstatus -c`.  Note that the older SunOS based VNC servers have slightly different options and behaviors.

## kvnc

The `kvnc` command can be used to start and stop VNC sessions.  The format is `kvnc [command] [desktops]`.  By default, this operates on the desktops associated with the current user.  For example, if the desktops used by the mosfire1 account were acting up and I wanted to restart all four of them, I would log in to the VNC server as user mosfire1 (i.e. `ssh mosfire1@mosfire`), I would then issue the command `kvnc stop servers` which would shut down all desktops associated with the mosfire1 user.  I could then start them again by issuing the command `kvnc start servers`.  I can also start or stop and individual desktop specifically (i.e. `kvnc stop telstatus`).

## kvncmanager

The `kvncmanager` script manages the scheduled shutdown and start up of the various VNC sessions based on the telescope schedule.

The advantage of shutting down and starting up the VNC sessions periodically is that destroying the desktop automatically closes any GUIs which might have been left running.  This is especially useful for some of our older IDL based GUIs as they occupy a license even when not in use.
