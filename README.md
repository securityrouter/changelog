The [securityrouter.org](http://securityrouter.org) project is a network operating system and software distribution based on OpenBSD which is developed and maintained by <a href="http://halon.io">Halon Security</a>. New systems are deployed by [downloading](http://dl2.halon.se/vsr/) a software image. The easiest way to update existing systems is to perform an [automatic update](http://securityrouter.org/wiki/Update) from within the product's administration.

New major versions (for example 3.5 which is based on OpenBSD 5.7) often contains numerous configuration syntax changes, which might render a previously working configuration invalid, and thus affect the operation of the system after an update. We therefore urge all users to perform such updates with caution; **take a snapshot** if running it as a virtual machine, or at least **backup the plain-text configuration** and **monitor the update** on the screen/[console](http://securityrouter.org/wiki/Serial_console), so that you can perform recovery or roll back to an older software version (using our help), if necessary.

There is an [RSS feed](https://github.com/halonsecurity/securityrouter.org/releases.atom) available.

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
