## Get AD Computers
```powershell
Get-AdComputer -Filter * -Properties * | Select Name, IPv4Address
```