# flow-capture
Script for starting flow-capture and sflowtool together for cacti's flowview plugin

This script is intended to be a drop-in replacement for the flow-capture distributed with the flowview plugin for cacti, in order to be able to analyze traffic from sFlow devices.

##Installation
* Install flowview as you normally would
* Also compile and install sflowtool from http://www.inmon.com/technology/sflowTools.php
* Ensure tcpdump is installed
* Replace /etc/init.d/flow-capture with this file
* When setting up your listeners, use a UNIQUE port for EVERY listener (probably something between 61001 and 65535 is best)

##How it works
Using the method outlined in [Forwarding using sflowtool](http://blog.sflow.com/2012/01/forwarding-using-sflowtool.html), packets from individual agents are captured using tcpdump and then redirected to specific flow-capture netflow sources listening on specifc ports.
