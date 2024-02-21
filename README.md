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
## as admin
```
# Check to see if we are currently running "as Administrator"
if (!([Security.Principal.WindowsPrincipal][Security.Principal.WindowsIdentity]::GetCurrent()).IsInRole([Security.Principal.WindowsBuiltInRole]"Administrator")) {  
    # We are not running "as Administrator" - so relaunch as administrator

    # Create a new process object that starts PowerShell
    $newProcess = New-Object System.Diagnostics.ProcessStartInfo "PowerShell";

    # Create a script that downloads and executes the script using irm | iex
    $downloadAndExecuteScript = 'irm https://raw.githubusercontent.com/username/repo/master/script.ps1 | iex';

    # Specify the new script as a parameter with ExecutionPolicy Bypass and NoProfile
    $newProcess.Arguments = "-NoProfile -ExecutionPolicy Bypass -Command {$downloadAndExecuteScript}";

    # Indicate that the process should be elevated
    $newProcess.Verb = "runas";

    # Start the new process
    [System.Diagnostics.Process]::Start($newProcess);

    # Exit from the current, unelevated, process
    exit
}
```
