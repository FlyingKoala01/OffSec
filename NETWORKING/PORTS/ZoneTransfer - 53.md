Information disclosure, port should never be open and returns potentially useful subdomains
```
dig axfr @machine_ip machine_domain_name >> dig_results.txt
```

Format output

```
cat dig_results | grep machine_domain_name | grep IN | awk '{print $1}' | sort -u
```

