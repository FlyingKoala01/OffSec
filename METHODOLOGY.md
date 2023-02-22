## Port scanning
	For TCP -> 
```
sudo nmap -vvv -sS -A -Pn -n --min-rate 5000 -p- -oN machine_ports.txt machine_ip 
```
	For UDP ->
```
sudo nmap -v -sU -T5 -oN machine_ports_udp.txt machine_ip 
```

## Service Enumeration

Check for service version and search exploits in [https://www.exploit-db.com/](https://www.exploit-db.com/) for the version numbers

## HTTP Enumeration

```
gobuster dir -w SecLists/Discovery/Web_Content/big.txt -u http://machine / -q -n -o output_file.txt -t 50
```
Once we get a few directories, visit them **curl** them 

### Search for Subdomains

```
wfuzz -c -w /usr/share/dnsrecon/subdomains-top1mil-500.txt -u machine_ip -H "Host:FUZZ.machine_name" --hc 301 
```

Chance hc parameter to ignore that code
