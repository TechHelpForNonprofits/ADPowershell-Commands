# ADPowershell-Commands
Helpful Powershell commands for Active Directory

#You may need to set your execution policy if these commands won't work
Set-ExecutionPolicy -ExecutionPolicy -Bypass

#Find user accounts that haven't logged in for 90 days or more; if you want to save to a file you would add  "| -Path c:\OldAccounts.csv" to the end w/o quotes
Search-ADAccount -UsersOnly -AccountInactive -TimeSpan 90.00:00:00 | Select-Object Name,LastLogonDate | Sort-Object LastLogonDate

#
