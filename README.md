Logwatch for grsecurity enabled kernels
=

What's this?
-

This is a couple of configuration files and parsing scripts for Logwatch to parse
messages for a couple of non-standard services. 

Installation
-

1. Copy `conf/services/service.conf` to `/etc/logwatch/conf/services`
2. Copy `scripts/services/service` to `/etc/logwatch/scripts/services`
3. Make the script in `/etc/logwatch/scripts/services` executable 

Substitute [service] with the service which you want to install. Currently this 
repository holds the following services: 

* grsec
* vnstat

Testing 
-

For testing I'm using the logwatch utility with output redirected to stdout. 
For testing grsec I use `paxtest` to generate some log entries.

`$ paxtest kiddie`

`$ logwatch --output stdout --range Today`
