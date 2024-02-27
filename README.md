# powershell
## rm  -rf 
```
rm -fo -r
```
## display installed appx
```
Get-AppxPackage | Select Name, PackageFullName | Out-Host
```
## display installed apps
```
winget list
```
## create shortcut
```
$WshShell = New-Object -comObject WScript.Shell
$Shortcut = $WshShell.CreateShortcut("$Home\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup\CapsToChangeInputLanguage.lnk")
$Shortcut.TargetPath = "$Home\caps-to-change-input-languages-autohotkey\CapsToChangeInputLanguage.ahk"
$Shortcut.Save()
```
## wget
```
$WebClient=New-Object Net.WebClient
$Uri='https://raw.githubusercontent.com/chubbyhippo/ahk/master/CapsToChangeInputLanguage.ahk'
$WebClient.DownloadFile($Uri, "$Home\downloads\CapsToChangeInputLanguage.ahk")
```
## unzip
```
Expand-Archive -Path $Home\downloads\windows-main.zip
```
## run bat
```
cmd.exe -/c Run.bat
```
## run remote script
```
irm https://something.ps1 | iex
```
## set profile
### as admin
```
New-Item -path $PROFILE.AllUsersAllHosts -type file -force
notepad.exe $PROFILE.AllUsersAllHosts
```
## alias
```
Set-Alias -Name docker -Value podman
```
