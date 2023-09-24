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
$WebClient=New-Object Net.WebClient; 
$Uri='https://raw.githubusercontent.com/chubbyhippo/ahk/master/CapsToChangeInputLanguage.ahk';
$WebClient.DownloadFile($Uri, "$Home\downloads\CapsToChangeInputLanguage.ahk");
```
