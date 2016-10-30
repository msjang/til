
```
cd /var/log
tail -F syslog
```

```
Aug 31 17:46:31 msjang tftpd[11196]: tftpd: trying to get file: XXXXXX-1.0.04-OTA.img
Aug 31 17:46:31 msjang tftpd[11196]: tftpd: serving file from /hdd01/tftpboot
Aug 31 17:55:25 msjang tftpd[11196]: tftpd: read: Connection refused
Aug 31 17:55:40 msjang tftpd[11465]: tftpd: trying to get file: XXXXXX-1.0.04-OTA.img
Aug 31 17:55:40 msjang tftpd[11465]: tftpd: serving file from /hdd01/tftpboot
Aug 31 17:55:54 msjang tftpd[11465]: tftpd: read: Connection refused
```

```
Aug 31 16:09:01 msjang CRON[6380]: (root) CMD (  [ -x /usr/lib/php5/maxlifetime ] && [ -x /usr/lib/php5/sessionclean ] && [ -d /var/lib/php5 ] && /usr/lib/php5/sessionclean /var/lib/php5 $(/usr/lib/php5/maxlifetime))
Aug 31 16:17:01 msjang CRON[6617]: (root) CMD (   cd / && run-parts --report /etc/cron.hourly)

Aug 31 16:26:07 msjang cinnamon-screensaver-dialog: pam_ecryptfs: seteuid error

Aug 31 16:35:45 msjang kernel: [806866.222415] nemo[2405]: segfault at 3007551f ip 00007f3363406297 sp 00007ffe577fe350 error 4 in libglib-2.0.so.0.4002.0[7f33633a2000+106000]

Aug 31 16:39:29 msjang NetworkManager[1201]: <info> (eth1): carrier now OFF (device state 100, deferring action for 4 seconds)
Aug 31 16:39:33 msjang NetworkManager[1201]: <info> (eth1): device state change: activated -> unavailable (reason 'carrier-changed') [100 20 40]
Aug 31 16:39:33 msjang NetworkManager[1201]: <info> (eth1): deactivating device (reason 'carrier-changed') [40]
Aug 31 16:39:33 msjang NetworkManager[1201]: <info> Policy set 'eth0' (eth0) as default for IPv4 routing and DNS.

Aug 31 16:39:38 msjang NetworkManager[1201]: <info> (eth1): carrier now ON (device state 20)
Aug 31 16:39:38 msjang NetworkManager[1201]: <info> (eth1): device state change: unavailable -> disconnected (reason 'carrier-changed') [20 30 40]

Aug 31 16:39:38 msjang kernel: [807099.796214] asix 3-2:1.0 eth1: link up, 100Mbps, full-duplex, lpa 0xC5E1

Aug 31 16:43:13 msjang dhclient: DHCPREQUEST of 192.168.111.27 on eth0 to 192.168.111.1 port 67 (xid=0x7cab8503)
Aug 31 16:43:13 msjang dhclient: DHCPACK of 192.168.111.27 from 192.168.111.1
Aug 31 16:43:13 msjang dhclient: bound to 192.168.111.27 -- renewal in 2802 seconds.

Aug 31 16:43:13 msjang NetworkManager[1201]: <info> (eth0): DHCPv4 state changed renew -> renew
Aug 31 16:43:13 msjang NetworkManager[1201]: <info>   address 192.168.111.27
Aug 31 16:43:13 msjang NetworkManager[1201]: <info>   prefix 24 (255.255.255.0)
Aug 31 16:43:13 msjang NetworkManager[1201]: <info>   gateway 192.168.111.1
Aug 31 16:43:13 msjang NetworkManager[1201]: <info>   nameserver '10.0.0.2'
Aug 31 16:43:13 msjang NetworkManager[1201]: <info>   nameserver '10.0.0.5'

Aug 31 16:43:13 msjang dbus[1043]: [system] Activating service name='org.freedesktop.nm_dispatcher' (using servicehelper)
Aug 31 16:43:13 msjang dbus[1043]: [system] Successfully activated service 'org.freedesktop.nm_dispatcher'
```