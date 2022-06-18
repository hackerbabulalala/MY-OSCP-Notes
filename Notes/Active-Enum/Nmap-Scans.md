
-------
NMAP
-------

```
 >>> sudo nmap 10.11.0.128 -p- -sV -vv --open --reason
 ```
 ```
 >>> nmap 10.1.1.1 --open -oG scan-results; cat scan-results | grep "/open" | cut -d " " -f 2 > exposed-services-ips
```
```
>>> nmap -sV -sC -p- -T4 $IP --open
```
```
>>> nmap -A -T4 -p- $IP
```
```
>>> nmap -p 1-65535 -sV -sS -A -T4 $IP/24 -oN nmap.txt
```
```
>>> nmap -sV -sU -T4 -A -v $IP/24
```
```
>>> nmap --script=vuln* $IP
```
```
>>> nmap -sC -sV -O -oA nmap/initial $IP
```
```
>>> nmap -sC -sV -O -p- -oA nmap/full $IP 												  [ Initial Scan ]
```
```
>>> nmap -sC -sV -O -p- -oA nmap/full $IP												    [ Full Scan ]
```
```
nmap -v -p- -sT -T4 -sV  $IP 														            [ TCP Deep_One ]
```


------
NSE
------

```

Finding Scripts : 
>>> locate .nse | grep [port name]
>>> ls -la /usr/share/nmap/scripts/  | grep -e ‘[ port name ]’


What This Script Do??
>>> nmap --script-help [script name]


Vulnerability Scanning : 
>>> nmap --script vuln $IP

>>> nmap -p 80 --script=all $IP 								[ A-Z Scripts on target , may take an hours ]

>>> nmap -p 80 --script=http*vuln* $IP 										[ use all HTTP Scripts ]


[ entire network for a directory traversal vulnerability ]
>>> nmap -p 80 --script=http-vuln-cve2010-2861 $IP/24     


```





