# ADPowershell-Commands
Helpful Powershell commands to check status of user and computer accounts on Active Directory
<br/>
<br/>

#You may need to set your execution policy if these commands won't work
```powershell 
Set-ExecutionPolicy -ExecutionPolicy -Bypass
```
#Find user accounts that haven't logged in for 90 days or more
```powershell
Search-ADAccount -UsersOnly -AccountInactive -TimeSpan 90.00:00:00 | Select-Object Name,LastLogonDate | Sort-Object LastLogonDate
```
#Similarly you can search for computers that haven't logged in for a period of time
```powershell
 Search-ADAccount -ComputersOnly -AccountInactive -TimeSpan 120.00:00:00 | Select-Object Name,LastLogonDate | Sort-Object LastLogonDate
 ```
#Find user accounts that are disabled
```powershell
Search-ADAccount -UsersOnly -AccountDisabled | Select-Object SamAccountName
```
#Find user accounts that have passwords that never expire
```powershell
Search-ADaccount -UsersOnly -PasswordNeverExpires | select-object SamAccountName
```
<br/>
<br/>
<i>#If you want to save results from any of these commands to a file add  "| -Path c:\OldAccounts.csv" to the end w/o quotes</i><br/>
