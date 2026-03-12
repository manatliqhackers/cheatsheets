## netexec
```bash
nxc ldap 10.10.11.10 -u 'john' -p 'password!' --bloodhound --collection ALL --dns-server 10.10.11.10
```

## rousthound
```bash
rusthound -d local.htb -u 'john' -p 'password!' -f "DC01.local.htb" -z
```

## bloodhound-python
```bash
bloodhound-python -u 'john' -p 'password!' -d local.htb --collectionmethod All --zip
```