## Get Deleted Users
```powershell
Get-ADObject -Filter 'isDeleted -eq $true -and objectClass -eq "user"' -includedeletedobjects -properties objectsid, lastknownparent, objectguid
```

## Restore Deleted User
```powershell
Get-ADObject -IncludeDeletedObjects -Filter {objectsid -eq 'S-1-5-21-1392491010-1358638721-2126982587-1111'} | Restore-ADObject
```

## Verify Changes
```powershell
Get-ADObject -Filter 'Name -eq "cert_admin"' -Properties * | Format-List
```