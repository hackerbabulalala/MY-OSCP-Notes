
--------
  Network Enum
--------

Network Discovery aka 'netdiscover' : 

```
netdiscover -i eth0 -r $IP/24
```


What Is My Network Range : 

```
ipcalc 10.10.10.10
```

Arp Scan : 

```
arp-scan $IP/24
```


Listen To ICMP requests : 

```
tcpdump -i tun0  icmp
```



--------
DNS Enumeration
--------

NMAP DNS Hostnames Lookup : 

```
nmap -F --dns-server <dns server ip> <target ip range>
```


Host Lookup : 

```
host -t ns megacorpone.com
```


Reverse Lookup Brute Force - find domains in the same range : 

```
for ip in $(seq 155 190);do host 50.7.67.$ip;done |grep -v "not found"
```


Perform DNS IP Lookup : 

```
dig a domain-name-here.com @nameserver
```


Perform MX Record Lookup : 

```
dig mx domain-name-here.com @nameserver
```


Perform Zone Transfer with DIG : 

```
dig axfr domain-name-here.com @nameserver
```


DNS Zone Transfers ( Windows ) : 

```
nslookup -> set type=any -> ls -d blah.com
```


Linux DNS zone transfer : 

```
dig axfr blah.com @ns1.blah.com
```


Dnsrecon DNS Brute Force : 

```
dnsrecon -d TARGET -D /usr/share/wordlists/dnsmap.txt -t std --xml ouput.xml
```


Dnsrecon DNS List : 

```
dnsrecon -d megacorpone.com -t axfr
```


DNSEnum : 

```
dnsenum zonetransfer.me
```


--------
To Be Continued
--------




