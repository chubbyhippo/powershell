# powershell
## rm  -rf 
```
rm -fo -r
```
## display installed appx
```
Get-AppxPackage | Select Name, PackageFullName | Out-Host
```
## create shortcut
```
$WshShell = New-Object -comObject WScript.Shell
$Shortcut = $WshShell.CreateShortcut("$Home\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup\CapsToChangeInputLanguage.lnk")
$Shortcut.TargetPath = "$Home\caps-to-change-input-languages-autohotkey\CapsToChangeInputLanguage.ahk"
$Shortcut.Save()
```
