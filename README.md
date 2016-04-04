The [securityrouter.org](http://securityrouter.org) project is a network operating system and software distribution based on OpenBSD which is developed and maintained by <a href="http://halon.io">Halon Security</a>. New systems are deployed by [downloading](http://dl2.halon.se/vsr/) a software image. The easiest way to update existing systems is to perform an [automatic update](http://securityrouter.org/wiki/Update) from within the product's administration.

New major versions (for example 3.5 which is based on OpenBSD 5.7) often contains numerous configuration syntax changes, which might render a previously working configuration invalid, and thus affect the operation of the system after an update. We therefore urge all users to perform such updates with caution; **take a snapshot** if running it as a virtual machine, or at least **backup the plain-text configuration** and **monitor the update** on the screen/[console](http://securityrouter.org/wiki/Serial_console), so that you can perform recovery or roll back to an older software version (using our help), if necessary.

There is an [RSS feed](https://github.com/halonsecurity/securityrouter.org/releases.atom) available.

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
