# How to set nic as monitor mode for wireshark

set monitor mode
```
$ sudo -s

# ifconfig wlan0 down
# iwconfig wlan0 mode monitor
# ifconfig wlan0 up

# iwconfig wlan0
wlan0     IEEE 802.11abgn  Mode:Monitor  Tx-Power=15 dBm   
          Retry short limit:7   RTS thr:off   Fragment thr:off
          Power Management:off

# wireshark &
```

```
ifconfig wlan0 down
iwconfig wlan0 mode monitor
ifconfig wlan0 up
iwconfig wlan0
wireshark &
```

check addresses to observe
```
# ifconfig wlan-l-0 | grep HWaddr
wlan-l-0  Link encap:Ethernet  HWaddr 00:30:0D:90:61:10  
# ifconfig wlan-h-0 | grep HWaddr
wlan-h-0  Link encap:Ethernet  HWaddr 00:30:0D:90:61:20  
```

capture filter
```
ether host 00:30:0D:90:61:10 or ether host 00:30:0D:90:61:20
```
