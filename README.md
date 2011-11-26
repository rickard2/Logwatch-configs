Logwatch for grsecurity enabled kernels
=

What's this?
-

This is a configuration file and parsing script for Logwatch to parse messages 
for grsecurity enabled kernels. The purpose is to detect any configuration errors
which could lead to some services not functioning properly. 

It's pretty basic so far, if you make any improvements please do share them.


Installation
-

1. Copy grsec.conf to /etc/logwatch/conf/services
2. Copy grsec to /etc/logwatch/scripts/services
3. Make grsec script executable 

`$ cp grsec.conf /etc/logwatch/conf/services/  
$ cp grsec /etc/logwatch/scripts/services/  
$ chmod +x /etc/logwatch/scripts/services/grsec`


Testing 
-

For testing I'm using paxtest to generate some log entries and then and logwatch 
with --output stdout and --range Today to see if the paxtest output is included. 

`$ paxtest kiddie  
$ logwatch --output stdout --range Today`
