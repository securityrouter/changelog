The [securityrouter.org](http://securityrouter.org) project is a network operating system and software distribution based on OpenBSD which is developed and maintained by <a href="http://halon.io">Halon Security</a>. New systems are deployed by [downloading](http://dl2.halon.se/vsr/) a software image. The easiest way to update existing systems is to perform an [automatic update](http://securityrouter.org/wiki/Update) from within the product's administration.

New major versions (for example 3.5 which is based on OpenBSD 5.7) often contains numerous configuration syntax changes, which might render a previously working configuration invalid, and thus affect the operation of the system after an update. We therefore urge all users to perform such updates with caution; **take a snapshot** if running it as a virtual machine, or at least **backup the plain-text configuration** and **monitor the update** on the screen/[console](http://securityrouter.org/wiki/Serial_console), so that you can perform recovery or roll back to an older software version (using our help), if necessary.

There is an [RSS feed](https://github.com/halonsecurity/securityrouter.org/releases.atom) available.

## 3.7-p1
Unreleased
- **`Bug`** Fixed regression since 3.7 (pledge-related) where some programs aborted because of `TZ` path
- **`Bug`** Applied [5.9 errata](http://www.openbsd.org/errata59.html) up to #009, including [CVE-2016-2105 to 9](https://www.openssl.org/news/secadv/20160503.txt)

## 3.7
Released on 2016-04-25
- **`New`** Based on [OpenBSD 5.9](http://www.openbsd.org/59.html)
 - SMP network stack improvements
 - Xen paravirtualizion support
 - Initial IEEE 802.11n wireless support
 - New [`etherip`](http://man.openbsd.org/OpenBSD-current/man4/etherip.4) Ethernet tunneling (RFC 3378) interface
 - New [`pair`](http://man.openbsd.org/OpenBSD-current/man4/pair.4) Ethernet encapsulation interface
 - New [EIGRP](http://man.openbsd.org/OpenBSD-current/man5/eigrpd.conf.5) routing daemon
 - IPv6 support for pflow (NetFlow) transport
 - IKEv2 interoperability with OS X El Capitan
 - Support for new hardware, including network adapters from Intel and Realtek
- **`Imp`** Ability to enable/disable clustering (sasyncd) without restarting IKE daemons
- **`Bug`** Prevent SIGPIPE when doing cleartext IKE packet capture in `isakmpd`
- **`Dep`** Moved [`ikev2`](http://man.openbsd.org/OpenBSD-current/man5/iked.conf.5) to separate `ike {` context for more accurate validation

## 3.6
Released on 2015-11-20
- **`New`** Based on [OpenBSD 5.8](http://www.openbsd.org/58.html)
 - New MPLS pseudowire driver [`mpw`](http://www.openbsd.org/cgi-bin/man.cgi/OpenBSD-current/man4/mpw.4?query=mpw&amp;sec=4)
 - Many improvements to [BGP](http://securityrouter.org/wiki/BGP), [OSPF](http://securityrouter.org/wiki/OSPF) and LDP (MPLS)
 - The same network range can now be assigned to multiple interfaces
 - MTU of VLAN devices can now be set independently from the parent interface's MTU
 - Jumbo frames on PC Engines' [APU](http://www.pcengines.ch/apu.htm) and Halon's [HSR-603](http://securityrouter.org/wiki/File:Hsr-603.png)
 - Support for the NX bit on i386 for better W^X enforcement
 - Support for new hardware, and improved network drivers
- **`New`** [VPLS](https://github.com/rwestphal/openbsd-ldpd/wiki/VPLS-basic-test-setup) (layer 2) MPLS support
- **`New`** Interface [route priority](http://securityrouter.org/wiki/Route_priority)
- **`Imp`** Uses `AUTOCONF6` for [router solicitation](http://securityrouter.org/wiki/IPv6#DHCPv6_client_and_router_solicitation) instead of `rtsold`
- **`Dep`** The default Diffie-Hellman group from IKEv1 has been changed to modp3072 (15)

## 3.5-r1
Released on 2015-07-30
- **`New`** Firewall ([pf.conf](http://www.openbsd.org/cgi-bin/man.cgi/OpenBSD-current/man5/pf.conf.5?query=pf%2econf)) editor got support for new syntax such as prio, queue, etc
- **`New`** New "basic" (non-JavaScript) firewall editor which is much faster when working with large rulesets
- **`Bug`** Regressions (since 3.5) in the first-run config disk population and `pkg_*` settings resolved

## 3.5
Released on 2015-05-27
- **`New`** Based on [OpenBSD 5.7](http://www.openbsd.org/57.html) with many improvements, such as
 - The load balancer (relayd) supports source-hash for L3 (redirections) and [SNMP](http://cvsweb.openbsd.org/cgi-bin/cvsweb/~checkout~/src/share/snmp/OPENBSD-RELAYD-MIB.txt?rev=1.1)
 - BIND has been removed, use [unbound](http://securityrouter.org/wiki/DNS_cache) instead
 - nginx has been replaced with OpenBSD's [own httpd](http://www.openbsd.org/papers/httpd-slides-asiabsdcon2015.pdf)
 - Support for new hardware, and improved network drivers
- **`Imp`** The firewall page loads faster with many rules
- **`Imp`** Automatic firewall rule sorting has been replaced by a "Sort" button
- **`Bug`** Make [clusterd](http://securityrouter.org/wiki/Clustering) and [configure](http://securityrouter.org/wiki/Configure) UTF-8 aware, to prevent corruption of non-ASCII
- **`Bug`** Empty persistent tables were overwritten by the firewall page
- **`Bug`** Fix issue on web admin's IPsec page with quoted strings containing syntax tokens
- **`Dep`** The load balancer has renamed the "ssl" keyword to "tls"
- **`Dep`** The load balancer is TLSv1.2 only by default, you need to manually enable other protocols

## 3.4-r1
Released on 2015-03-19
- **`New`** Added support for [LLDP](http://securityrouter.org/wiki/LLDP)
- **`New`** Added support for [vether](http://www.openbsd.org/cgi-bin/man.cgi/OpenBSD-5.6/man4/vether.4?query=vether) interfaces
- **`Sec`** Patched OpenSSL in regards to [security advisory as of 19 mar 2015](http://www.openbsd.org/errata56.html#020_openssl)
- **`Bug`** Bug on load balancing page with "pftag"
- **`Bug`** Regression in the HTTPS SOAP API (since 3.4)
- **`Dep`** gmt0 was renamed to utc in SOAP API

## 3.4-p1
Released on 2015-01-12
- **`Imp`** Backup (cluster) nodes can use NTP (`ntpd`) even without working egress IP, via cluster port
- **`Bug`** Web admin server regression; now uses [nginx](http://www.openbsd.org/cgi-bin/man.cgi/OpenBSD-5.6/man8/nginx.8?query=nginx&amp;manpath=OpenBSD%2d5%2e6)

## 3.4
Released on 2014-12-11
- **`New`** Based on [OpenBSD 5.6](http://www.openbsd.org/56.html)
 - Includes the [Unbound](http://securityrouter.org/wiki/DNS_cache#Unbound) DNS cache
 - Reverse proxy (`match ... forward to`) support in the [load balancer](http://www.openbsd.org/cgi-bin/man.cgi/OpenBSD-current/man5/relayd.conf.5?query=relayd%2econf)
 - Support for new hardware, including network adapters from Broadcom and Realtek
- **`Imp`** Add [SIP proxy](http://securityrouter.org/wiki/Proxies#SIP_proxy) to interface page
- **`Imp`** Support searching logs larger than 2 GB
- **`Bug`** Fixes regression on load balancer status page
- **`Bug`** Fixes issue when loading/reloading isakmpd
- **`Bug`** Fixes issue with dhinfod
- **`Bug`** Fixes issue with router advertisement and DHCPv6 with some clients

## 3.3-p2
Released on 2014-08-11
- **`Bug`** Re-configure IKE daemon (isakmpd) if it crashes and is restarted by the watchdog
- **`Bug`** Mitigate a threading issue, to prevent rare dead-locks during startup and reconfiguring

## 3.3-p1
Released on 2014-06-09
- **`Sec`** Fix OpenSSL CVE-2014-0195, 2014-0221, 2014-0224 and 2014-3470
- **`Imp`** Removed deprecated browser-specific CSS3 options (Mozilla, Opera)
- **`Imp`** Enable auto-scroll on keypress in web terminal
- **`Bug`** Allow more than 1000 items to be saved (PHP introduced input data limit)
- **`Bug`** Update firmware boot data on OpenBSD 5.0 systems to prevent boot issue

## 3.3
Released on 2014-05-13
- **`New`** Based on [OpenBSD 5.5](http://www.openbsd.org/55.html)
- **`New`** Added [VXLAN](http://sr.wiki.halon.se/wiki/VXLAN) to grammar and web admin
- **`New`** Supports new hardware such as
 - VMware's VMXNET3 network interfaces and paravirtual SCSI
 - VirtIO's paravirtual SCSI and random number devices
 - Many new Intel platforms and NICs, such as the AES-NI capable Atom [C2000](http://www.intel.com/content/www/us/en/intelligent-systems/rangeley/atom-c2000-product-family-based-platforms-overview.html)
 - PC Engine's [APU](http://pcengines.ch/apu.htm)
- **`Imp`** Support copy-pasting directly into web admin's HTML5 terminal
- **`Imp`** Accurately choose a local IPsec endpoint address to send probe pings from
- **`Imp`** [Ed25519](http://ed25519.cr.yp.to) SSH signatures
- **`Imp`** Allow omitting pflow (NetFlow/IPFIX) sender address
- **`Bug`** Fixes an issue where the IKE daemon `isakmpd` wouldn't run with many addresses configured
- **`Bug`** Do not use cluster rdomain for updating on active cluster nodes without default route
- **`Bug`** Fixes an issue where the VPN server `npppd` could fail to start

## 3.2-r2p1
Released on 2014-04-08
- **`Bug`** Patched OpenSSL ["heartbleed"](http://heartbleed.com) vulnerability (CVE-2014-0160)

## 3.2-r2
Released on 2014-04-03
- **`New`** Route priorities
- **`New`** Add reserved host from DHCP lease page
- **`Imp`** Load balancers on front page in web admin
- **`Imp`** Show cancel URL when testing a commit
- **`Imp`** Ping with LAN addresses if a tunnels local endpoint is 0.0.0.0/0
- **`Imp`** Warn about pflow protocol 9 soon being deprecated
- **`Bug`** Web admin failed to set IKE phase 2 mode to none
- **`Bug`** Basic setup erased aliases if having multiple IPs
- **`Bug`** isakmpctl capture could fail to show decrypted packets
- **`Bug`** Cluster push configuration button were broken
- **`Bug`** System could run out of bpf interfaces

## 3.2-r1
Released on 2014-01-08
- **`New`** Added `x-superuser` [login class](http://sr.wiki.halon.se/wiki/Users)
- **`Imp`** Added [skeleton file](http://sr.wiki.halon.se/wiki/Skeleton_files) for the DHCP server
- **`Imp`** Support running [router solicitation](http://sr.wiki.halon.se/wiki/IPv6), syslog and NTP in [routing domains](http://sr.wiki.halon.se/wiki/Routing_domains)
- **`Imp`** Allowed web terminal to poll [backend](http://sr.wiki.halon.se/wiki/Backend) even when browser tab is in background
- **`Imp`** Added more IPv6 auto-configuration settings to web administration
- **`Imp`** Strip last dot from DHCPv6 search domain
- **`Imp`** Various minor improvements
- **`Bug`** Don't announce SLAAC prefixes when running a DHCPv6 server
- **`Bug`** Resolved issue when filtering logs based on firewall label on amd64
- **`Bug`** Resolved ping-from-self through NAT issue
- **`Bug`** Resolved issue when moving VLANs from an unconfigured interface

## 3.2
Released on 2013-11-08
- **`New`** Based on OpenBSD 5.4
- **`New`** Router advertisement (v6) can announce DNS
- **`Imp`** Router advertisement doesn't announce prefix if DHCP managed
- **`Imp`** Sandboxed SSH server
- **`Imp`** Disabled private SNMP community by default
- **`Imp`** Various minor improvements
- **`Bug`** Issue with load balancer's host page when using IPs in relays

## 3.1-p7
Released on 2013-11-01
- **`New`** Buy feature licenses from within product's interface
- **`New`** Support for new HSR-603 model
- **`New`** Support for [reset](http://sr.wiki.halon.se/wiki/Recovery) button on HSR-1204 and ALIX
- **`Imp`** Real-time decrypted IKE packets (isakmpctl capture)
- **`Imp`** Simplified and unified DHCP page
- **`Imp`** Support temperature sensors in ALIX
- **`Imp`** Firewall supports interface addressing and DNS in DHCP/BGP setups
- **`Imp`** Use bidirectional IPsec flows by default
- **`Imp`** Better validation of FQDNs as DHCP hosts
- **`Imp`** Make HTTP/SSH servers and pflow support [routing domains](http://sr.wiki.halon.se/wiki/Routing_domains)
- **`Imp`** Require both sender and server for pflow interfaces
- **`Imp`** Various minor improvements
- **`Bug`** HTTP server didn't respect rsa-key and x509-certificate
- **`Bug`** Scrolling didn't always freeze
- **`Bug`** SSL was checked when adding new load balancer listeners
- **`Bug`** Couldn't type @ in web terminal
- **`Bug`** Do not create sessions for unauthorized web admin clients

## 3.1-p6
Released on 2013-09-02
- **`Bug`** Management interfaces couldn't be disabled on administration page
- **`Bug`** IKE lifetime wasn't maintained on IPsec page
- **`Bug`** Tables was printed with an extra semi-colon on firewall page
- **`Bug`** NTP client didn't use updated name servers (for example DHCP)

## 3.1-p5
Released on 2013-08-09
- **`Imp`** Gracefully discard invalid host names in vApp deployment
- **`Bug`** Warning on front page if no graphs are available
- **`Bug`** XML warning on non-VMware system's interface page

## 3.1-p4
Released on 2013-08-07
- **`Imp`** Support new HSR-1200 series hardware
- **`Bug`** Support non-standard gateway IP in update firmware
- **`Bug`** No longer consume VMware channels without vApp
- **`Bug`** Handle configuration without groups on firewall page
- **`Bug`** Various minor bugs fixed

## 3.1-p3
Released on 2013-07-29
- **`New`** Network setup guide in OVF (VMware vCenter)
- **`Imp`** Minor web administration improvements
- **`Bug`** Disabled SMP due to threading regression in OpenBSD 5.3

## 3.1-p2
Released on 2013-07-24
- **`Imp`** Restructured CLI menu
- **`Imp`** Subscription licenses are more tolerant to connectivity issues
- **`Imp`** Faster boot by disabling floppy drives in kernel
- **`Imp`** Minor web administration improvements
- **`Bug`** Could generate invalid VPN server configuration, regression

## 3.1-p1
Released on 2013-07-15
- **`New`** New IKE debugging tool (isakmpctl)
- **`Imp`** Support for VIA temperature sensors
- **`Imp`** Perl modules needed by pkg_add included
- **`Bug`** Cluster failed to detect successful synchronizations

## 3.1
Released on 2013-07-10
- **`New`** Based on OpenBSD 5.3 (with patches from head)
- **`New`** Support for KVM Virtio para-virtualized drivers
- **`New`** Added load balancer methods; least states, source hash, random
- **`New`** Support for NetFlow 9 and 10 (IPFIX) in `pflow`
- **`New`** Temperature sensors on graph page
- **`Imp`** Added IPsec lifetime to plain-text configuration and interface
- **`Imp`** Added DHCP server options 66 and 67
- **`Imp`** Allow DHCP relay on CARP interface
- **`Bug`** Only allow valid advbase values
- **`Bug`** NTP client reload fixes

## 3.0-p33
Released on 2013-06-28
- **`Imp`** Load balancer (relayd) performance improved
- **`Imp`** Graphs page display load balancer names
- **`Imp`** IPsec IKE tunnels page displays DH group number
- **`Imp`** Firewall page removes outer brackets on lists without space
- **`Bug`** Load balancer page didn't display correctly if name ended with a digit
- **`Bug`** Load balancer (relayd) didn't support more than 20 relays
- **`Bug`** Cluster discovery (hdpd) don't exit when missing serial

## 3.0-p32
Released on 2013-05-31
- **`Imp`** PPTP proxy timeout increased
- **`Imp`** Load balancer page lists available listen addresses
- **`Imp`** Internet failover doesn't require load balancer license
- **`Imp`** Terminal emulator page input improved
- **`Bug`** Load balancer page didn't handle multiple listeners and SSL
- **`Bug`** License page's link to renewals didn't work

## 3.0-p31
Released on 2013-05-21
- **`Imp`** System disks are grown to disk's size (CF, etc) into new data partition
- **`Imp`** Buffered software update without storage disk on grown systems
- **`Imp`** Support 1000base* on Intel's SFP+
- **`Imp`** Interface descriptions on graphs page
- **`Imp`** Ability to change CARP password from interface page
- **`Imp`** Sort DHCP leases based on lease times
- **`Imp`** Web terminal's input synchronised
- **`Imp`** Support `sis` interfaces
- **`Imp`** Improved Ethernet media handling
- **`Imp`** Allow svlan (QinQ) on trunk (LAG) interfaces
- **`Imp`** Reserved DHCP hosts excluded from ranges
- **`Bug`** IPsec labels such as "to host" was interpreted as a resolvable hostname
- **`Bug`** Graph daemon `statd` warned about full disk too many times

## 3.0-p30
Released on 2013-04-11
- **`New`** Mirror (SPAN ports) on bridges
- **`Imp`** Keep logs and graphs when rebooting if using a storage disk
- **`Imp`** Faster software updates (writes data to disk asynchronous)
- **`Imp`** Flush all GRE states when enabling the PPTP proxy
- **`Imp`** `storageupdate` has support for explicit (IPv) -4 and -6
- **`Bug`** Max addresses on bridges wasn't configurable in web administration
- **`Bug`** Load balancer's wizard was to strict on detecting potential conflicts

## 3.0-p29
Released on 2013-03-11
- **`New`** New model VSR-Lite available for purchase
- **`New`** Support for PC Engine's ALIX system boards
- **`Imp`** VPN servers support search domain and routes for Apple OSX and iOS clients
- **`Imp`** Other minor improvements
- **`Bug`** dhsyncd would fail to start if any carp interface was down

## 3.0-p28
Released on 2013-02-25
- **`New`** New CLI command `replace-swap` in `configure`
- **`Imp`** Support for Dell R320
- **`Imp`** Edit buttons in tables
- **`Imp`** Support `rdomain` and `proxy-arp` in cluster activation
- **`Imp`** Other minor improvements

## 3.0-p27
Released on 2013-02-20
- **`Imp`** Support for more Broadcom NICs
- **`Imp`** Other minor improvements
- **`Bug`** Could not enable free mode (VSR-Free) without serial

## 3.0-p26
Released on 2013-02-05
- **`Imp`** VLAN on trunk interfaces
- **`Imp`** Suppress repeated cluster errors
- **`Imp`** Other minor improvements
- **`Bug`** When configuring partial date and time

## 3.0-p25
Released on 2012-12-14
- **`New`** Microsoft Hyper-V support
- **`New`** Ability to use additional disk as storage for logs, etc
- **`New`** Ability to update with verification using storage disk
- **`Imp`** Improved performance during commit/test
- **`Imp`** Question on drain/flush load balancer node pausing
- **`Imp`** Changed Subversion format to FSFS
- **`Imp`** Improved loading time on firewall page with many rules
- **`Imp`** Overall improvements
- **`Bug`** IP ranges in macros on firewall page
- **`Bug`** Load balancer wizard didn't work with missing statement
- **`Note`** Reserved routing domain 239-255

## 3.0-p24
Released on 2012-11-21
- **`New`** The `proxy-arp` makes it possible to use [LAN network in VPN server](http://sr.wiki.halon.se/wiki/VPN_server#Proxy_ARP)
- **`Imp`** Cluster (`hdpd`) keeps information about dead hosts
- **`Imp`** Improved macro/table presentation on Network > Firewall
- **`Imp`** Many load balancer improvements
 - Proper source-tracking per redirect
 - Summarise statistics for multiple "listen on"
 - Ability to enable/disable hosts in all relays/redirects
 - Creates automatic rules for relays (tagged relayd)
 - Wizard for adding relays and redirects
 - User interface for global settings
 - [MIB](http://sr.wiki.halon.se/wiki/Load_balancing#SNMP_traps) for traps
- **`Imp`** User interface for SNMP settings on System > SNMP
- **`Bug`** Fixed problem when renaming duplicate macros/tables
- **`Bug`** Exports on Configuration > Revision management named properly
- **`Bug`** Fixed issue with `statd` removing graphs when redirects is down

## 3.0-p23
Released on 2012-10-25
- **`Imp`** Allow more than 4 VPN server groups by creating /dev/tunX dynamically
- **`Imp`** Visual noise when displaying all rulesets on firewall page removed
- **`Imp`** Permit hyphens in the host part in FQDNs (search-domain and host-name)
- **`Imp`** Other minor improvements

## 3.0-p22
Released on 2012-10-22
- **`New`** Real-time graphs
- **`New`** Graphs for firewall states
- **`New`** Login banner in web administration
- **`New`** Highlight text in CLI output with | mark
- **`Imp`** Forwarding (firewall/routing) performance improved
- **`Imp`** Ability to configure DNS, routes, etc per VPN group
- **`Imp`** Always allow DHCP on VPN interfaces for dhinfod to work
- **`Imp`** Shortcuts to rule and state statistics on Firewall page
- **`Imp`** Better logging when using SOAP's commandRun
- **`Imp`** Go directly to deploy/diff when saving on clear-text page
- **`Imp`** Ability to restore the terminal using CLI's "reset"
- **`Imp`** Display line numbers of configuration error page
- **`Imp`** Firewall page now visually renders more protocols
- **`Imp`** Less obstructive reloading of VPN server
- **`Imp`** Other minor improvements
- **`Bug`** Bug in PHP/CURL's DNS reloading remedied
- **`Bug`** Memory leak in UUID generation
- **`Bug`** Invalid netmask displayed as 0.0.0.0 on basic setup page

## 3.0-p21
Released on 2012-09-25
- **`Imp`** Web admin settings for VPN-server client routes
- **`Imp`** Usability improvements
- **`Bug`** Real-time firewall log issue resolved

## 3.0-p20
Released on 2012-09-24
 - New: VPN-server (L2TP/PPTP) supports client routes
 - Bug: Issue with IPsec 3DES key generation button resolved

## 3.0-p19
Released on 2012-09-10
- **`New`** VPN-server (L2TP) NAT-T support
- **`New`** VPN-server (L2TP/PPTP) DNS suffix support
- **`New`** Replaced [`configure`](http://wiki.halon.se/SR/Configure) "diff" with new "compare" command
- **`Imp`** Various graphical usability improvements
- **`Bug`** Saving a firewall macro with multiple items resulted in duplicate brackets
- **`Bug`** L2TP passphrase not saved when editing existing server

## 3.0-p18
Released on 2012-09-02
- **`New`** VSR-Free, a free license
- **`New`** License subscription, option to automatically downloads license keys
- **`Imp`** [CLI](http://wiki.halon.se/SR/CLI) can install and remove license keys
- **`Imp`** Log failed password attempts via HTTPS
- **`Imp`** Added support for option 82 in the dhcp-relay
- **`Bug`** Multiple negations on firewall page didn't render properly

## 3.0-p17
Released on 2012-08-22
- **`New`** [DHCPv6](http://wiki.halon.se/SR/IPv6#DHCPv6) server, client and prefix delegation
- **`New`** IPv6 router solicitation client
- **`New`** [User classes](http://wiki.halon.se/SR/Users), including read-only users (login.conf)
- **`New`** Web graph layout is customisable and auto saved
- **`Imp`** Ability to renew DHCP leases
- **`Imp`** Web improvements for Apple iOS and Microsoft IE 9
- **`Imp`** Web terminal has better scroll-back
- **`Imp`** Web shows disk usage on System > Hardware
- **`Imp`** Changed system paths according to BSD defaults
- **`Imp`** [CLI](http://wiki.halon.se/SR/CLI) parsing improved with quoted strings
- **`Imp`** Web settings stored in HTML5 local storage
- **`Imp`** Updated jQuery
- **`Bug`** Resolved cluster memory leak in backend
- **`Bug`** Resolved issue with /tmp getting full
- **`Bug`** Resolved web cluster page script error
- **`Bug`** Suppressed warning when confirming deployment
- **`Bug`** Spelling corrections

## 3.0-p16
Released on 2012-07-10
- **`New`** Diagnostics > Terminal with full ANSI support
- **`New`** Working copy allows for atomic apply of multiple changes
- **`Imp`** Ability to tag configuration revisions with a message
- **`Imp`** Ability to cancel a pending configuration test
- **`Imp`** Network > Interface got statistics
- **`Imp`** Network > Interface got PPPoE support
- **`Imp`** Network > Firewall supports negation of addresses
- **`Imp`** Network > Basic setup got PPPoE support
- **`Imp`** Network > DHCP server lists connected clients (leases)
- **`Imp`** PPPoE interface automatically adds routes and rules
- **`Imp`** Welcome texts on first boot
- **`Imp`** New layout on login screen
- **`Imp`** Highlights save or warns about unsaved changes
- **`Imp`** Validating function configCheck() in SOAP API
- **`Imp`** Default arguments in SOAP API
- **`Imp`** Command for showing licenses in CLI
- **`Bug`** Now validates reserved DHCP host's name more strictly
- **`Bug`** No longer kicked out of console when setting root password
- **`Bug`** Resolved issue with dhsyncd causing sawtooth CPU usage

## 3.0-p15
Released on 2012-06-11
- **`Imp`** Support for ne (NE1000) interfaces (used by Parallels Desktop)
- **`Imp`** Changed the fail-path when activating clustering
- **`Bug`** Error on first page for un-configured interfaces resolved
- **`Bug`** Issue when duplicating rules on the firewall page resolved

## 3.0-p14
Released on 2012-06-08
- **`New`** Introduced cluster support using SSL certificates
- **`New`** Introduced PPPoE support
- **`New`** Introduced RADIUS support for PPTP and L2TP server with groups
- **`New`** Last ethernet interface automatically becomes cluster sync on installation
- **`New`** Possibility to update a cluster node through other node via sync interface
- **`New`** New replace command in CLI configure
- **`New`** Load balancer shows statistics for layer 3 (redirects)
- **`New`** Keyboard layout support for video consoles
- **`Imp`** Internal IPC moved from TCP to Unix sockets for increased local security
- **`Imp`** Firewall page supports "received-on" routing domains
- **`Imp`** Friendly warning on password change in web administration
- **`Imp`** DHCP server supports clustering
- **`Imp`** DHCP server supports DHCP option 43
- **`Imp`** Make DHCP server leases persistent across reboots
- **`Imp`** Possibility to only change one of the DHCP range values
- **`Imp`** Router advertisements supports clustering
- **`Imp`** Basic setup displays unplugged cable correctly
- **`Imp`** Support Intel 10/100 network cards (fxp)
- **`Imp`** HTTPS server supports certificates and keys in configuration
- **`Imp`** Renamed "cd" to "edit" in CLI configure
- **`Imp`** License page more detailed explains license keys
- **`Imp`** Overview page consumes less CPU
- **`Imp`** Load balancer inherits default SSL certificate unless overridden
- **`Imp`** Load balancer page layout improved
- **`Imp`** Web browser cache is automatically flushed after software updates
- **`Imp`** Users "admin" and "root" can force reboots from CLI
- **`Imp`** Users "admin" and "root" can perform a factory reset from CLI
- **`Imp`** Allowed all users to view packets in tcpdump from CLI
- **`Imp`** License, copyright and credit page added under Help page
- **`Imp`** Prevents users from removing themselves by mistake
- **`Imp`** IPsec tunnel ping test works on /0 networks
- **`Imp`** Hide shutdown button on hardware page by default
- **`Bug`** Bug in tcpbench resolved (patch sent upstream)
- **`Bug`** Display error on DHCP page resolved
- **`Bug`** The PPTP proxy has issues with clients sending GRE too early
- **`Bug`** Monotonic time were not always used for wake ups
- **`Bug`** Change of order of some keys in configuration didn't triggering a commit
- **`Bug`** Parsing error on load balancer page resolved
- **`Bug`** Syslog didn't log with host name
- **`Bug`** DHCP settings link on interface page didn't work for all interface types

## 3.0-p13
Released on 2012-03-22
- **`Bug`** DHCP relay regression issue resolved

## 3.0-p12
Released on 2012-03-20
- **`New`** Hardware detection for Halon HSR-1000

## 3.0-p11
Released on 2012-03-16
- **`New`** [Load balancer](http://wiki.halon.se/SR/Load_balancing) user interface
- **`New`** [FTP proxy](http://wiki.halon.se/SR/Proxies) for NAT called `interface X { ftp-proxy`
- **`New`** [PPTP proxy](http://wiki.halon.se/SR/Proxies) for NAT called `interface X { pptp-proxy`
- **`Imp`** Firewall user interface supports `divert`
- **`Bug`** Load balancer stability issue patched
- **`Bug`** Suppressed unnecessary `interface-group` events
