Most network configuration manuals still refer to `ifconfig` and `route`
as the primary network configuration tools,
but `ifconfig` is known to behave inadequately in modern network environments.
They, and the whole [net-tools suite][15], are being deprecated,
but most Linux distros still include them.
They should be replaced by the [iproute2 suite][14].
iproute2 (usually shipped in a package called iproute or iproute2)
consists of several tools, of which the most important are `ip` and `tc`.
`ip` controls IPv4 and IPv6 configuration and `tc` stands for traffic control.
The iproute2 collection contains the following command-line utilities:
`ip`, `ss`, `bridge`, `rtacct`, `rtmon`, `tc`, `ctstat`, `lnstat`,
`nstat`, `routef`, `routel`, `rtstat`, and `arpd`.

what about ethtool, netifd, nm-tool, nmcli, nm-online

* Why nm-tool is no longer available in Ubuntu 15.04? - http://askubuntu.com/questions/617067/why-nm-tool-is-no-longer-available-in-ubuntu-15-04
* 9 Linux ethtool Examples to Manipulate Ethernet Card (NIC Card) - http://www.thegeekstuff.com/2010/10/ethtool-command/
* Fun with ethtool - http://www.linuxjournal.com/content/fun-ethtool
*  Stop using telnet to test network connectivity - http://scotte.github.io/2015/03/stop-using-telnet/

The NetworkManager daemon attempts to make networking configuration and operation as painless and automatic as possible by managing the primary network connection and other network interfaces, like Ethernet, WiFi, and Mobile Broadband devices. NetworkManager will connect any network device when a connection for that device becomes available, unless that behavior is disabled. Information about networking is exported via a D-Bus interface to any interested application, providing a rich API with which to inspect and control network settings and operation.

####################
* also see
    * [tshark - Monitor network traffic tutorial](http://www.linuxuser.co.uk/tutorials/monitor-network-traffic-tutorial)
    * [10 Free Server & Network Monitoring Tools that Kick Ass](http://sixrevisions.com/tools/10-free-server-network-monitoring-tools-that-kick-ass/)
    * [Raspberry Pi – control your network traffic with Nagios](https://developer-blog.net/en/hardware-2/raspberry-pi-control-your-network-traffic-with-nagios/)
    * [Raspberry Pi and Distributed Network Monitoring: Iperf](https://netbeez.net/2014/08/19/raspberry-pi-and-distributed-network-monitoring-iperf/)
    * [How to Build a Portable Hacking Station with a Raspberry Pi and Kali Linux](http://lifehacker.com/how-to-build-a-portable-hacking-station-with-a-raspberr-1739297918)

* Tools for Querying / Configuring IP Network
    * [`ip`][17] shows and manipulates routing, devices, policy routing, and tunnels
    * [`ifconfig`][16] is a network interface configuration, control, and query tool.
    The `ifconfig` command is deprecated and you can replace `ifconfig` by `ip link`.
    * [`tc`][19] (traffic control) configures and controls the Linux kernel's
    network scheduler to show and manipulate network traffic control settings
    * [`ifrename`][13] allows to rename wireless network interfaces based on various
    static criteria to assign a consistent name to each interface.
    * [`arp`][20] (address resolution protocol) is used to translate protocol addresses to
    hardware interface addresses.
    The `arp` command is deprecated and you can replace `arp -na` by `ip neigh`.
    * [`route`][27] command is used to show/manipulate the IP routing table.
    It is primarily used to setup static routes to specific host or networks via an interface.
    * [`nslookup`][28] is a tool for querying the Domain Name System (DNS) to obtain domain name
    or IP address mapping or for any other specific DNS record.
* Tools for Querying / Configuring WiFi
    * [`iw`][02] show / manipulate wireless devices and their configuration.
    It is also used in the system startup scripts of many operating systems.
    * [`iwconfig`][18] is used to display and change the parameters of the
    wireless network interface (e.g. interface name, frequency, SSID).
    It may also be used to display the wireless statistics (extracted from `/proc/net/wireless`).
    * [`iwpriv`][34] is the companion tool to `iwconfig`. `iwpriv` deals with
    parameters and setting specific to each driver (as opposed to `iwconfig`
    which deals with generic ones).
    * [`iwlist`][12] allow to initiate scanning and list frequencies, bit-rates, encryption keys, etc.
    **Example Usage:** `iwlist wlan0 scan`
* Tools for Monitoring / Scanning IP Network
    * [`nmap`][29] (network mapper) is a security tool for network exploration,
    q security scanning, and auditing.
    `nmap` sends specially crafted packets to discover hosts and services on a computer network,
    thus creating a "map" of the network.
    * [`ettercap`][30] is a network security tool for man-in-the-middle attacks on LAN.
    It is capable of intercepting traffic on a network segment, capturing passwords,
    and conducting active eavesdropping against a number of common protocols.
    * [`netstat`][09] (network statistics) is a command-line tool that displays
    network connections for TCP (both incoming and outgoing),
    routing tables, and a number of network interface and network protocol statistics.
    **Example Usage:** `netstat -ie`
    * [`nicstat`][10] prints network traffic, packets or Kb/s read and written.
    Its a utility like `top` for network interface card (NIC).
    It displays information and statistics about all your network card such as packets,
    kilobytes per second, average packet sizes and more.
    **Example Usage:** `nicstat -i wlan0 1`
* Tools for Monitoring / Scanning WiFi
    * [`wavemon`][07] is a ncurses-based monitoring application for wireless network devices.
    It displays continuously updated information about signal levels, as well as,
    wireless-specific and general network information.
    **Example Usage:** `wavemon wlan0`
    * [`iwevent`][08] is another command line tool that displays wireless events
    received through the [RTNetlink socket][06].
    Each line displays the specific wireless event which describes
    what has happened on the specified wireless interface.
    **Example Usage:** `iwevent`
    * [`iwspy`][33] is used to set a list of addresses to monitor in a
    wireless network interface and to read back quality of link information for each of those.
* IP Network Packet Analysis
    * [`tcpdump`][31] is a common packet analyzer that runs under the command line.
    It allows the user to display TCP/IP and other packets being transmitted or
    received over a network to which the computer is attached.
    * [`wireshark`][32] (orginally called `ethereal`) is the world's de facto
    network protocol analyzer letting you do deep inspection of hundreds of protocols,
    live capture, and offline analysis.
    * [`tshark`][35] the command-line version of Wireshark.
    The main advantage of tshark is that it can be used in scripts.
    Its main disadvantage is that it does not have a GUI.
* IP Networking Utilities
    * [`ping`][25] (Packet Internet Gropper) is like a sonar pulse sent to detect another IP address.
    It is used to test the connection and latency between two network connections.
    * [`traceroute`][26] (trace route) is a diagnostic tool for displaying the route
    (path) and measuring transit delays of packets across an IP network.
    * [`netcat` or `nc`][22] is a [highly functional][21] Unix utility which reads and writes data
    across network connections, using TCP or UDP protocol.
    It is designed to be a reliable "back-end" tool that can
    be used directly or easily driven by other programs and scripts.
    * [`ncat][23] is a feature-packed networking utility which reads and writes
    data across networks from the command line.
    Ncat was written a much-improved reimplementation of `netcat`. `ncat` will work with IPv4,
    IPv6, and has many potential uses.
    * [`telnet`][24] (teletype network) is both a protocol which is part of the TCP/IP suite
    providing a bidirectional interactive text-oriented communication facility
    and a und line ser interface to the protocol.
    **Example Usage:** `telnet 192.168.8.1`

[Howto Check Wireless link quality in Ubuntu Linux](http://www.ubuntugeek.com/howto-check-wireless-link-quality-in-ubuntu-linux.html)
[A tcpdump Tutorial and Primer](https://danielmiessler.com/study/tcpdump/)
http://www.cyberciti.biz/networking/nmap-command-examples-tutorials/
http://www.thegeekstuff.com/2010/08/tcpdump-command-examples/
http://technet.microsoft.com/en-us/library/cc786759(v=ws.10).aspx
http://www.tecmint.com/ip-command-examples/
http://www.computerhope.com/unix/unslooku.htm
http://www.computerhope.com/unix/route.htm
http://www.thegeekstuff.com/2012/04/route-examples/
http://pcsupport.about.com/od/commandlinereference/p/tracert-command.htm
http://www.cyberciti.biz/faq/unix-ping-command-examples/
http://www.linux.org/threads/tcp-ip-utilities-ping-and-traceroute.4848/
http://www.thegeekstuff.com/2009/11/ping-tutorial-13-effective-ping-command-examples/
http://www.sanfoundry.com/10-ping-command-usage-examples-linux/
http://www.computerhope.com/unix/arp.htm
http://www.cyberciti.biz/faq/linux-traffic-shaping-using-tc-to-control-http-traffic/
http://www.cyberciti.biz/faq/linux-ip-command-examples-usage-syntax/
https://www.digitalocean.com/community/tutorials/how-to-use-iproute2-tools-to-manage-network-configuration-on-a-linux-vps
http://www.computerhope.com/unix/ip.htm
http://linoxide.com/linux-command/use-ip-command-linux/
[Wireless Tools for Linux / Wireless Applications for Linux](http://www.hpl.hp.com/personal/Jean_Tourrilhes/Linux/Tools.html#links)
[Cheat Sheets](http://packetlife.net/library/cheat-sheets/)

WiFi Configuration Via Command Line
* [Step-by-step: Connect to WiFi network from command line in Linux](http://www.blackmoreops.com/2014/09/18/connect-to-wifi-network-from-command-line-in-linux/)
* [wireless on the command line](http://substack.net/wireless_from_the_command_line_in_linux)
* [The Pain of Connecting to WPA Wi-Fi on the Linux Command Line](http://www.sevenforge.com/2009/07/28/connecting-to-wpa-wifi-on-the-command-line/)
* [NetworkConfigurationCommandLine/Automatic](https://help.ubuntu.com/community/NetworkConfigurationCommandLine/Automatic)
* [How do I connect to a WPA wifi network using the command line?](http://askubuntu.com/questions/138472/how-do-i-connect-to-a-wpa-wifi-network-using-the-command-line)
* [Connect to WiFi network through Ubuntu terminal](http://askubuntu.com/questions/294257/connect-to-wifi-network-through-ubuntu-terminal)
* [Wireless network configuration](https://wiki.archlinux.org/index.php/Wireless_network_configuration)
* [How to Find The Best Wi-Fi Channel For Your Router on Any Operating System](http://www.howtogeek.com/197268/how-to-find-the-best-wi-fi-channel-for-your-router-on-any-operating-system/)

####################

# MAC Address and OUI Lookup
* [OUI (MAC address) lookup script](http://www.backtrack-linux.org/forums/showthread.php?t=29819)
* [Resolving MAC Address from IP Address](http://unix.stackexchange.com/questions/120153/resolving-mac-address-from-ip-address-in-linux)
* [Change mac address with macchanger Linux command](http://linuxconfig.org/change-mac-address-with-macchanger-linux-command)
* [Wireshark · OUI Lookup Tool](https://www.wireshark.org/tools/oui-lookup.html)

####################



####################

Multicast Domain Name System (mDNS)
(http://www.multicastdns.org/) is one of the features of Bonjour, included in Mac OS X 10.2 or later.
mDNS resolves host names to IP addresses within small networks that do not include a local name server.
It is a zero-configuration service,
using essentially the same programming interfaces,
packet formats and operating semantics as the unicast Domain Name System (DNS).
When an mDNS client needs to resolve a host name,
it sends an IP multicast query message that asks the host having that name to identify itself.
That target machine then multicasts a message that includes its IP address.
All machines in that subnet can then use that information to update their mDNS caches.

On the Internet at large, a DNS name such as "www.apple.com" must be resolved
to a numbered IP address before your computer can connect to the server.
A domain name system (DNS) server normally provides this name resolution service for your computer.
Your Internet service provider or network administrator normally provides a local DNS server for your use.

Conversely, mDNS allows computers on a local network, such as home or small office,
to look up each others' names and addresses without a DNS server.
Each computer knows its own name and responds to requests for that name automatically via IP multicast.

Anywhere that a you could normally use a DNS name such as "www.apple.com",
you could instead enter the Bonjour name of the computer on the local network.
To indicate that the name should be looked up using local multicast instead of a standard DNS query,
all Bonjour host names end with the extension ".local."
This helps avoid confusion between names that are local Bonjour computer names
("mycomputer.local") and globally unique DNS names ("www.apple.com").

####################


# SSH - Remote Unix Work
[Tips for remote Unix work: SSH, screen, and VNC](http://shebang.brandonmintern.com/tips-for-remote-unix-work-ssh-screen-and-vnc/)

# Establishing a Connection
You can use `iw` to connect to an AP directly if and only if the AP has:

* No encryption
* Uses WEP for encryption

If you need to connect to an AP with WPA or WPA2 encryption,
then you must use [`wpa_supplicant`][03].

```bash
# connect to an AP that has encryption disabled, where its SSID is foo
iw wlan0 connect foo

# if you have two APs with the SSID foo, and you know the one you want to
# connect to is on the frequency 2432, you can specify the frequency to use
iw wlan0 connect foo 2432

# connect to an AP that uses WEP, you can use:
iw wlan0 connect foo keys 0:abcde d:1:0011223344
```

# WiFi Status and Configuration
All WiFi dongles are not the same.
They differ in performance based upon the chip set used in their design.
You can assess details about the capability of your WiFi dongle via [`iw`][02].
`iw` is a new CLI configuration utility for wireless devices.
The old tool `iwconfig` is deprecated, never the less, you might still find it in use.

```bash
# list information about the currently associated wireless network
$ iwconfig wlan0
wlan0     IEEE 802.11bgn  ESSID:"74LL5"
          Mode:Managed  Frequency:2.462 GHz  Access Point: 00:12:93:A4:8A:F0
          Bit Rate=54 Mb/s   Tx-Power=27 dBm
          Retry  long limit:7   RTS thr:off   Fragment thr:off
          Power Management:on
          Link Quality=63/70  Signal level=-47 dBm
          Rx invalid nwid:0  Rx invalid crypt:0  Rx invalid frag:0
          Tx excessive retries:0  Invalid misc:5471   Missed beacon:0
$
```

First thing is to get device capabilities for all devices:

```bash
# get device capabilities for all devices, such as band information (2.4 GHz, and 5 GHz),
# and 802.11n information
iw list
```

The next step is to see what wireless networks are available in your area.
A utility called `iwlist` provides all sorts of information about your wireless environment.
To scan your environment for available networks, do the following:

```bash
# scanning for an access point
sudo iwlist wlan0 scan

# alternative
sudo iw dev wlan0 scan
```

To listen to events concerning you WiFi link, use these commands:

```bash
# listening to events
iw event

# see the auth/assoc/deauth/disassoc frames
iw event -f

# timing information is added
iw event -t
```

To determine if you are connected to an AP (or not), and if you are the
last TX rate used you can use the command below:

```bash
# getting link status
iw dev wlan0 link
```

# Getting Station Statistics
To get station statistic information such as the amount of tx/rx bytes,
the last TX bit rate (including [MCS values][05]) you can do:

```bash
$ iw dev wlan0 station dump
Station 00:1f:90:b4:8a:80 (on wlan0)
	inactive time:	7976 ms
	rx bytes:	29886939
	rx packets:	419177
	tx bytes:	49091
	tx packets:	1535
	tx retries:	18
	tx failed:	0
	signal:  	-43 dBm
	signal avg:	-43 dBm
	tx bitrate:	48.0 MBit/s
	authorized:	yes
	authenticated:	yes
	preamble:	long
	WMM/WME:	no
	MFP:		no
	TDLS peer:		no
```

* **TDLS**, or Tunneled Direct Link Setup is a technology that enables devices to
link directly to one another when connected to a traditional WiFi network.
* **WMM/WME**, or Wireless Multimedia Extensions (WME), also known as WiFi Multimedia (WMM),
provides basic Quality of service (QoS) features to IEEE 802.11 networks.

If you want to get specific statistics against a peer you station is
communicating with you can use the following:

```bash
sudo iw dev wlan1 station get <peer-MAC-address>
```

In the case of a STA the above <peer-MAC-address>
would be the MAC address of your AP.

# Setting TX Power

```bash
# set the txpower by using either the device interface name of the respective phy.
iw dev <devname> set txpower <auto|fixed|limit> [<tx power in mBm>]
iw phy <phyname> set txpower <auto|fixed|limit> [<tx power in mBm>]
```

IEEE-802.11 was designed with [`power saving`][04] in mind for stations.
To assist stations with power saving, Access Points (APs) are designed to buffer frames
for a station when that station is in power save mode and
to transmit them later to the station when the AP knows the station will listen.
When a station is in power save mode, it turns off its transmitter and receiver to preserve energy.
It takes less power for a station to turn its receiver on to listen to
frames than to turn it its transmitter on to transmit frames.
For this reason, it's more power-efficient for an AP to inform a station if it has
buffered frames present on the AP than to have the station poll the AP querying if frames are present.

```bash
# to enable power save by default
sudo iw dev wlan0 set power_save on

# to query the current power save settings
iw dev wlan0 get power_save
```

# Setting Frequency or Channel
```bash
# set frequency
iw dev wlan0 set freq 2412 [HT20|HT40+|HT40-]

# set channel
iw dev wlan0 set channel 1 [HT20|HT40+|HT40-]
```

# IBSS / Ad-Hoc Networks
```bash
# join an IBSS / ad-hoc network
iw wlan0 set type ibss
iw wlan0 ibss join foo-adhoc 2412

# leaving an IBSS / ad-hoc network
iw wlan0 ibss leave
```

# What Devices Are Connected to Your Network
An easy way to scan your network to see what device are connected is to use [`nmap`][01].
With this you can find out if some unknown or unwanted device is connected to it.

Despite its popularity as a utility for network discovery and security auditing,
`nmap` isn't part of the base install for Ubuntu.
To install it, just do

    sudo apt-get install nmap

To begin your scan using `nmap -sP`,
which will run a ping scan on the specified network.
For instance, `nmap -sP 192.168.1.0/24` will scan the 256 hosts from
192.168.1.0 through 192.168.1.255 to see if they're available, and report back.

```bash
# ????
sudo nmap -v -sL 192.168.1.0/24

# ping scan on the specified network
sudo nmap -sP 192.168.1.0/24
```

To check to see what services are running on a box

```bash
# list what services are running
sudo nmap -sV 192.168.1.1
```

# Routing
_Routing_ is a means of sending an IP packet from one point to another.
In computer networking, a _router_ is a device responsible for forwarding network traffic.
On Linux and UNIX systems,
information on how packets are to be forwarded is stored in a
kernel structure called a _routing table_.
In effect, a routing table is a set of rules,
that is used to determine where data packets, traveling over an IP network, will be directed.
All IP-enabled devices, including computer hosts, routers, and switches, use routing tables.

Today, most of the multiuser systems (aka hosts) can be configured to act as a router.
So, a common routing algorithm can be specified that can be used by the router as well as by a host.
When a host can act like a router,
it is generally said that the host has an _embedded router_ functionality.
Such a host which has an embedded router functionality,
should never forward datagrams until and unless configured to do so (i.e. configured to act like a router).

The routing table can be used for both _static routing_ and _dynamic routing_.
Dynamic routing consists of the kernel making decisions as to which route,
out of multiple present routes, a packet should take.
Static routing is a form of routing that occurs when a router
uses a manually-configured routing entry,
rather than information from a dynamic routing protocol to forward traffic.

The data in routing table contains the following main entries:

Destination IP address
:   This  field represents the IP address of the destination.
    This IP address could be the address of a single host or could that be of a network.
IP address of next router
:   This entry gives the IP address of the next router which decides how to
    further send an IP data gram received on its interface.
Flags
:   This field provides information like destination IP address (specified above)
    is a host address or a network address or convey whether the next router
    (specified above) is really a next router or a directly connected interface.
Network interface specs
:   Some specification about the network interface the datagram should
    be passed for further transmission.

For further information and education, see

* [Introduction to Linux IP Routing Fundamentals (Part 1)](http://www.thegeekstuff.com/2012/04/ip-routing-intro/)

## Display the Routing Table
Each entry is nothing but an entry in the routing table (Linux kernel routing table).

```bash
# display the kernel routing table
$ sudo route -n
Kernel IP routing table
Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
0.0.0.0         192.168.1.1     0.0.0.0         UG    0      0        0 eth1
192.168.1.0     0.0.0.0         255.255.255.0   U     1      0        0 eth1

# using netstat
$ netstat -r
Kernel IP routing table
Destination     Gateway         Genmask         Flags   MSS Window  irtt Iface
default         Wireless_Broadb 0.0.0.0         UG        0 0          0 eth1
192.168.1.0     *               255.255.255.0   U         0 0          0 eth1

# the -n option means that you want numerical IP addresses displayed
$ netstat -rn
Kernel IP routing table
Destination     Gateway         Genmask         Flags   MSS Window  irtt Iface
0.0.0.0         192.168.1.1     0.0.0.0         UG        0 0          0 eth1
192.168.1.0     0.0.0.0         255.255.255.0   U         0 0          0 eth1
```

The output provides a detailed information in the destination IP addresses and their gateways.
The flag ‘U’ suggests that the route is up,
and the flag ‘G’ suggests that the router is to a gateway (router).
If this flag is not set then it can be assumed that the destination is directly connected.

```bash
# using the iproute2 suite
$ ip route list
default via 192.168.1.1 dev eth1  proto static
192.168.1.0/24 dev eth1  proto kernel  scope link  src 192.168.1.4  metric 1
```

## Diagnosing Routing Problems
http://www.coyotepoint.com/files/downloads/StaticRoutes.pdf

# Definitions and Concepts
All components that can connect into a wireless medium in a network are referred to as **stations**.
All stations are equipped with wireless network interface controllers (WNICs).
Wireless stations fall into one of two categories: wireless access points, and clients.

* **Access Points (APs)**, normally wireless routers, are base stations for the wireless network.
They transmit and receive radio frequencies for wireless enabled devices to communicate with.
* Wireless **clients** can be mobile devices such as laptops, personal digital assistants,
IP phones and other smartphones, or fixed devices such as desktops and workstations
that are equipped with a wireless network interface.

* **SoftAP** is short for Software enabled Access Point.
This is software that turns a computer that was not specifically made to be a
router into a Wireless Access Point.
It is often used interchangeably with the term "virtual router".
The advantage of SoftAP is the use of a regular cellphone,
for example, with a client antenna and data connection as an
Access Point to serve other wireless devices which do not have a data connection otherwise.
The wireless devices in the vicinity of the SoftAP enabled device,
which may not have the Internet access directly,
can use the Internet through the cellphone whose SoftAP is enabled.
This is called tethering.

The **basic service set (BSS)** is a set of all stations that can communicate with each other.
Every BSS has an identification (ID) called the BSSID,
which is the MAC address of the access point servicing the BSS.
There are two types of BSS:Independent BSS (also referred to as IBSS), and infrastructure BSS.

* An **independent BSS (IBSS)** is an ad hoc network that contains no access points,
which means they can not connect to any other basic service set (BSS).
* An **infrastructure BSS** can connect with other basic service set (BSS).

An **extended service set (ESS)** is a set of connected BSSs.
Access points in an ESS are connected by a distribution system.
Each ESS has an ID called the **SSID** which is a 32-byte (maximum) character string.

### Types of Wireless LANs
The IEEE 802.11 has two basic modes of operation: ad hoc mode and infrastructure mode.

* In **ad hoc mode**, mobile units transmit directly peer-to-peer.
There is no base and no one gives permission to talk.
This is accomplished using the Independent Basic Service Set (IBSS).
* In **infrastructure mode**, mobile units communicate through an access point that serves
as a bridge to other networks (such as Internet or LAN).

A **[WiFi Direct][06]**, also called WiFi P2P, network is another type of network where stations communicate peer to peer.
In a WiFi Direct group, the group owner operates as an access point and all other devices are clients.
There are two main methods to establish a group owner in the WiFi Direct group.

* In one approach, the user sets up a P2P group owner manually.
This method is also known as **Autonomous Group Owner** (autonomous GO).
* In the second method, also called **negotiation-based group creation**,
two devices compete based on the group owner intent value.
The device with higher intent value becomes a group owner and the second device becomes a client.
Group owner intent value can depend on whether the wireless device performs a
cross-connection between an infrastructure WLAN service and a P2P group,
remaining power in the wireless device, whether the wireless device is already a group owner in another group
and/or a received signal strength of the first wireless device.

A **bridge** can be used to connect networks, typically of different types.
A wireless Ethernet bridge allows the connection of devices on a wired Ethernet network to a wireless network.
The bridge acts as the connection point to the Wireless LAN.

A **wireless distribution system (WDS)** is a system enabling the wireless interconnection
of access points in an IEEE 802.11 network.
It allows a wireless network to be expanded using multiple access points without the
traditional requirement for a wired backbone to link them.

# Traffic Shaping
Traffic Shaping (a.k.a Bandwidth Shaping or Packet Shaping)
is an attempt to control network traffic by prioritizing network resources
and guarantee certain bandwidth based on predefined policy rules.
Traffic shaping uses concepts of traffic classification, policy rules,
queue disciplines and quality of service (QoS).

http://www.iplocation.net/tools/traffic-control.php

# Test for Internet Speed
You determine your Internet download speed right from a terminal window
by using the `wget` command to pull a file from a remote server.
The speed is displayed in the terminal when the file download has completed

```bash
$ wget -O /dev/null http://speedtest.wdc01.softlayer.com/downloads/test10.zip

--2014-12-24 16:00:44--  http://speedtest.wdc01.softlayer.com/downloads/test10.zip
Resolving speedtest.wdc01.softlayer.com (speedtest.wdc01.softlayer.com)... 208.43.102.250
Connecting to speedtest.wdc01.softlayer.com (speedtest.wdc01.softlayer.com)|208.43.102.250|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 11536384 (11M) [application/zip]
Saving to: ‘/dev/null’

100%[======================================>] 11,536,384  5.03MB/s   in 2.2s

2014-12-24 16:00:46 (5.03 MB/s) - ‘/dev/null’ saved [11536384/11536384]
$
```

[How to Test Internet Connection Speed using Speedtest-Cli on Ubuntu Server](http://ubuntuserverguide.com/2014/01/how-to-test-internet-connection-speed-using-speedtest-cli-on-ubuntu-server.html)

# Script for Wireless Stations Monitoring
Here is a [script][11] that provides live stats monitor of wireless stations' link quality
and some additional useful information regarding the
bit rate, Tx/Rx packets, wireless signal strength, etc.
<!-- -------- Start: Gist Code Snippet --------- -->
<style="padding: 5px; overflow: auto; font-family: Andale Mono,Lucida Console,Monaco,fixed,monospace; color: rgb(0, 0, 0); background-color: rgb(238, 238, 238); font-size: 12px; line-height: 14px; width: 90%;">
    <script src="https://gist.github.com/jeffskinnerbox/9277e3ee7961c47ec4c8.js"></script>
</style>
<!-- --------- End: Gist Code Snippet ---------- -->

## Sources
These are the major sources for the information and commands documented in this post.

* [Official Linux Wireless Wiki](http://wireless.kernel.org/en/users/Documentation)
* [Wireless Tools for Linux](http://www.hpl.hp.com/personal/Jean_Tourrilhes/Linux/Tools.htmlq)

## Requires More Research
These links should be explored to see what additional information
could be gathered for this cheat sheet.

* [Finding a device IP Address](http://www.cnx-software.com/2010/10/25/finding-a-device-ip-address/)

* [Find What Devices Are Connected to Network In Ubuntu](http://itsfoss.com/how-to-find-what-devices-are-connected-to-network-in-ubuntu/)
* [Wi-Fi on the Command Line](http://www.linuxjournal.com/content/wi-fi-command-line)
* [ Who is on my wifi?](http://forum.backbox.org/general-support/who-is-on-my-wifi/)
* [WiFinder is a Python Driven Roommate Warning System](http://hackaday.com/2014/06/28/wifinder-is-a-python-driven-roommate-warning-system/)

* [7 Things Wi-Fi Hackers Hope You Don't Know](http://www.nowiressecurity.com/articles/things_wi-fi_hackers_hope_you_dont_know.htm)
* [First Linux Release of Wi-Fi app inSSIDer Available to Download](http://www.omgubuntu.co.uk/2011/01/wi-fi-app-inssider-2-linux-alpha-released)

# Route
* [Linux route Add Command Examples](http://www.cyberciti.biz/faq/linux-route-add/)
* [The Linux ip Command – An Ostensive Overview](http://packetpushers.net/linux-ip-command-ostensive-definition/)

# Nmap
* [Beginner's Guide to Nmap](http://www.linux.com/learn/tutorials/290879-beginners-guide-to-nmap)
* [Top 30 Nmap Command Examples For Sys/Network Admins](http://www.cyberciti.biz/networking/nmap-command-examples-tutorials/)
* [Nmap Cheat Sheet](https://blogs.sans.org/pen-testing/files/2013/10/NmapCheatSheetv1.0.pdf)
* [Nmap Referasnce Guide](http://www.bandwidthco.com/whitepapers/netforensics/recon/nmap/NMAP%20Reference%20Guide.pdf)
* [NMAP - A Stealth Port Scanner](http://www.csc.villanova.edu/~nadi/csc8580/S11/nmap-tutorial.pdf)

# Zenmap
* [Zenmap](http://nmap.org/zenmap/)
* [An introduction to using Zenmap on Linux](http://www.maketecheasier.com/using-zenmap-on-linux/)
* [Zenmap Tutorial: Audit Your Networks using Nmap GUI](http://www.linux.com/learn/tutorials/381794-audit-your-network-with-zenmap)

# Kismet
* [How to use Kismet: A free Wi-Fi network-monitoring tool](http://searchsecurity.techtarget.com/video/How-to-use-Kismet-A-free-Wi-Fi-network-monitoring-tool?videoId=8eb0fc2d1aa26410VgnVCM1000000d01c80aRCRD)

# Arbitrary Network Packets
* [HOWTO: Crafting arbitrary network packets with socat](http://discourse.criticalengineering.org/t/howto-crafting-arbitrary-network-packets-with-socat/51/last)
* [socat: Linux / UNIX TCP Port Forwarder](http://www.cyberciti.biz/faq/linux-unix-tcp-port-forwarding/)



[01]:http://www.linux.com/learn/tutorials/290879-beginners-guide-to-nmap
[02]:http://wireless.kernel.org/en/users/Documentation/iw
[03]:http://wireless.kernel.org/en/users/Documentation/wpa_supplicant
[04]:http://wireless.kernel.org/en/developers/Documentation/ieee80211/power-savings
[05]:http://www.digitalairwireless.com.au/wireless-blog/recent/understanding-mcs-values.html
[06]:http://en.wikipedia.org/wiki/Wi-Fi_Direct
[07]:http://www.raspberrypi-spy.co.uk/2014/10/how-to-use-wavemon-to-monitor-your-wifi-connection/
[08]:http://linux.about.com/library/cmd/blcmdl8_iwevent.htm
[09]:http://www.binarytides.com/linux-netstat-command-examples/
[10]:http://www.cyberciti.biz/hardware/linux-install-nicstat-command-to-print-network-statistics-for-nics/
[11]:https://forum.openwrt.org/viewtopic.php?id=29075
[12]:http://linux.die.net/man/8/iwlist
[13]:https://www.debian-administration.org/article/502/Keeping_consistent_network_interface_names_with_ifrename
[14]:http://www.linuxfoundation.org/collaborate/workgroups/networking/iproute2
[15]:http://net-tools.sourceforge.net/
[16]:http://linuxcommand.org/man_pages/iwconfig8.html
[17]:http://linux.die.net/man/8/ip
[18]:http://linuxcommand.org/man_pages/iwconfig8.html
[19]:http://lartc.org/manpages/tc.txt
[20]:http://linux.die.net/man/8/arp
[21]:http://www.sans.org/security-resources/sec560/netcat_cheat_sheet_v1.pdf
[22]:http://nc110.sourceforge.net/
[23]:http://nmap.org/ncat/
[24]:http://www.telnet.org/
[25]:http://linux.die.net/man/8/ping
[26]:http://pcsupport.about.com/od/commandlinereference/p/tracert-command.htm
[27]:http://linux.about.com/od/commands/l/blcmdl8_route.htm
[28]:http://linux.die.net/man/1/nslookup
[29]:http://nmap.org/
[30]:http://linux.die.net/man/8/ettercap
[31]:http://www.tcpdump.org/manpages/tcpdump.1.html
[32]:https://www.wireshark.org/
[33]:http://linux.die.net/man/8/iwspy
[34]:http://linux.about.com/library/cmd/blcmdl8_iwpriv.htm
[35]:http://www.linuxuser.co.uk/tutorials/monitor-network-traffic-tutorial
[36]:
[37]:
[38]:
[39]:
[40]:

