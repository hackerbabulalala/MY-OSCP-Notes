------
Autorecon
------

```
autorecon -vv $IP 
python3 autorecon.py -ct 4 -cs 10 
autorecon -t targets.txt
```



------
One2Punch
------
So, the idea behind the script to generate a scan of 65,535 ports on the targets. The script use unicornscan to scan all ports, and make a list of those ports that are open. The script then take the open ports and pass them to nmap for service detection.


NOTE : Create a text file contains of our targets machine.

```
./onetwopunch.sh ip-range.txt tcp
./onetwopunch.sh -t ip-range.txt -p tcp
```


------
Netcat
------

If we have windows machine without nmap, we can use PSnmap(https://www.powershellgallery.com/packages/PSnmap/)

```
TCP Scan:
>>> nc -vvn -z $IP 0-65535
UDP Scan:
>>>nc -vvn -u -z $IP 0-65535
```

-----
Nikto Scan
-----

```
nikto -h $IP
nikto -h $IP -C all
```

-----
Banner-Grab
-----

```
nc -vvv $TARGET 80
telnet $TARGET 80
curl -vX $TARGET
whatweb $IP                                           # identifies all known services
```


-----
Auto-Scan
-----

```
git clone https://bitbucket.org/xaeroborg/python3-programs.git
python3 autoscan_v2.py {interface} {IP adress}
```




------
Legion-CLI
------

Installation
```
git clone https://github.com/carlospolop/legion.git /opt/legion
cd /opt/legion/git
./install.sh
ln -s /opt/legion/legion.py /usr/bin/legion
```

Usage

```
# Better Experiance ;
docker build -t legion  .
docker run -it legion bash
./legion.py
#list using the command;
(legion)> protos
(legion)> set protos ssh
(legion)> set intensity 3
(legion)> info
(legion)> help
(legion)> options
# Fullt Automatic;
(legion)> startGeneral
(legion)> set host 127.0.0.1
======================
```


------
Nmap-Automater
------

```
nmapAutomator <IP> All
nmapAutomator <IP> Full
```
