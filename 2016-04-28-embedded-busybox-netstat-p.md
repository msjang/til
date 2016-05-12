# How to enable 'netstat -p' on busybox

```
Enable the following flag at busybox
CONFIG_FEATURE_NETSTAT_PRG
```

Ref) Busybox, netstat, no -p
http://serverfault.com/questions/219984/busybox-netstat-no-p



Before
```
; ATOM side

# netstat -p
netstat: invalid option -- 'p'
BusyBox v1.22.1 (2016-04-18 10:52:29 KST) multi-call binary.

Usage: netstat [-ral] [-tuwx] [-enW]

Display networking information

        -r      Routing table
        -a      All sockets
        -l      Listening sockets
                Else: connected sockets
        -t      TCP sockets
        -u      UDP sockets
        -w      Raw sockets
        -x      Unix sockets
                Else: all socket types
        -e      Other/more information
        -n      Don't resolve names
        -W      Wide display

# which netstat
/bin/netstat

# ls -al /bin/netstat 
lrwxrwxrwx    1 1000     1000            19 Apr 25 10:01 /bin/netstat -> /bin/busybox.nosuid



; ARM side

# netstat -p
netstat: invalid option -- p
BusyBox v1.22.1 (2016-04-18 11:29:32 KST) multi-call binary.

Usage: netstat [-ral] [-tuwx] [-en]
```



Modify
```
; ATOM side

yocto/meta-intelce/recipes-core/busybox/busybox-1.22.1/defconfig
-# CONFIG_FEATURE_NETSTAT_PRG is not set
+CONFIG_FEATURE_NETSTAT_PRG=y

yocto/meta-yocto/recipes-core/busybox/busybox/poky-tiny/defconfig
-# CONFIG_FEATURE_NETSTAT_WIDE is not set
-# CONFIG_FEATURE_NETSTAT_PRG is not set
+CONFIG_FEATURE_NETSTAT_WIDE=y
+CONFIG_FEATURE_NETSTAT_PRG=y

yocto/meta/recipes-core/busybox/busybox/defconfig
-# CONFIG_FEATURE_NETSTAT_WIDE is not set
-# CONFIG_FEATURE_NETSTAT_PRG is not set
+CONFIG_FEATURE_NETSTAT_WIDE=y
+CONFIG_FEATURE_NETSTAT_PRG=y



; ARM side

build/defconfig b/build/defconfig
-# CONFIG_FEATURE_NETSTAT_PRG is not set
-# CONFIG_FEATURE_NETSTAT_WIDE is not set
+CONFIG_FEATURE_NETSTAT_PRG=y
+CONFIG_FEATURE_NETSTAT_WIDE=y
```



After
```
; ATOM side

root@intel_ce_linux:~# netstat -p
Active Internet connections (w/o servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name    
tcp        0      0 localhost.localdomain:42227 localhost.localdomain:webmin TIME_WAIT   -
tcp        1      0 (null):9999             (null):45996            CLOSE_WAIT  5439/wifiledctl
tcp        0      0 localhost.localdomain:42231 localhost.localdomain:webmin TIME_WAIT   -
tcp        0      0 (null):9999             (null):46133            TIME_WAIT   -
tcp        0      0 localhost.localdomain:webmin localhost.localdomain:42230 TIME_WAIT   -
tcp        0      0 localhost.localdomain:webmin localhost.localdomain:42227 TIME_WAIT   -
tcp        0      0 localhost.localdomain:webmin localhost.localdomain:42229 TIME_WAIT   -
tcp        0      0 (null):891              (null):60878            ESTABLISHED 3683/icepm_daemon
tcp        0      0 (null):9999             (null):46132            TIME_WAIT   -
tcp        0      0 localhost.localdomain:webmin localhost.localdomain:42231 TIME_WAIT   -
tcp        0      0 localhost.localdomain:42229 localhost.localdomain:webmin TIME_WAIT   -
tcp        0      0 localhost.localdomain:42228 localhost.localdomain:webmin TIME_WAIT   -
Active UNIX domain sockets (w/o servers)
Proto RefCnt Flags       Type       State         I-Node PID/Program name    Path
unix  2      [ ]         DGRAM                      7183 5021/hostapd        /var/run/hostapd/wlan-h-0
unix  3      [ ]         DGRAM                      1598 1758/syslogd        /dev/log
unix  2      [ ]         DGRAM                      6741 4967/hostapd        /var/run/hostapd/wlan-l-0
unix  3      [ ]         DGRAM                      4448 3716/log_main       /dev/log
unix  2      [ ]         DGRAM                      1730 2256/udevd          @/org/kernel/udev/udevd
unix  4      [ ]         DGRAM                      1726 2219/syslogd        /dev/log
unix  2      [ ]         DGRAM                      1736 2256/udevd          
unix  3      [ ]         DGRAM                      1735 2256/udevd          
unix  2      [ ]         DGRAM                       470 1761/klogd          
unix  2      [ ]         DGRAM                      4412 3759/dhclient       
unix  3      [ ]         DGRAM                      1734 2256/udevd          



; ARM side

# netstat -p
Active Internet connections (w/o servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name    
tcp        0      0 localhost:32993         localhost:10000         TIME_WAIT   -
tcp        0      0 localhost:32990         localhost:10000         TIME_WAIT   -
tcp        0      0 localhost:10000         localhost:32992         TIME_WAIT   -
tcp        0      0 localhost:33001         localhost:10000         TIME_WAIT   -
tcp        0      0 localhost:10000         localhost:33002         TIME_WAIT   -
tcp        0      0 localhost:10000         localhost:32994         TIME_WAIT   -
tcp        0      0 localhost:32996         localhost:10000         TIME_WAIT   -
tcp        0      0 localhost:10000         localhost:32995         TIME_WAIT   -
tcp        0      0 localhost:33000         localhost:10000         TIME_WAIT   -
tcp        0      0 localhost:10000         localhost:32997         TIME_WAIT   -
tcp        0      0 localhost:32991         localhost:10000         TIME_WAIT   -
Active UNIX domain sockets (w/o servers)
Proto RefCnt Flags       Type       State         I-Node PID/Program name    Path
unix  5      [ ]         DGRAM                       583 196/log_main        /dev/log
unix  2      [ ]         DGRAM                      5427 1393/dnsmasq        
unix  2      [ ]         DGRAM                       866 258/portmap         
```
