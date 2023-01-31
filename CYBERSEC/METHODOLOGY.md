## Port scanning
	For TCP -> 
```
sudo nmap -vvv -sS -A -Pn -n --min-rate 5000 -p- -oN box_name.txt box_ip 
```
	For UDP ->
```
sudo nmap -v -sU -T5 -oN box_name_udp.txt box_ip 
```

## Service Enumeration

Check for service version and search exploits in [https://www.exploit-db.com/](https://www.exploit-db.com/) for the version numbers

## HTTP Enumeration

```
gobuster -w SecLists/Discovery/Web_Content/big.txt -u http://ip_box/ -q -n -o output_file.txt
```
Once we get a few directories, visit them **curl** them 

### Search for Subdomains

