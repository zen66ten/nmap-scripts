
# Nmap NSE Scripts and Scans

## mop-discover.nse


[DECnet MOP](https://blogs.cisco.com/security/router-spring-cleaning-no-mop-required-again) (still shipped in Cisco IOS 15.x) in Cisco IOS/IOS-XE allows remote login via VTY by default.

 MOP RC is enabled by default on all ethernet devices and has to be explicitly disabled.
##
It can easily be checked if the Maintenance Operation Protocol (MOP) is enabled on a device if IP is known.

`nmap --script mop-discover.nse 192.168.1.1`

In case there is just layer 2 connectivity, the MAC address can be specified as follows:

`nmap --script mop-discover.nse --script-args target=01:02:03:04:05:06 -e eth0`

Requires root as it sends and receives raw ethernet frames
