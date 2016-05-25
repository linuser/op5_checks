
#Information: https://github.com/DemisR/check_winbulog

#HowToRun On Windows Server

Copy script check_backup.ps1 in NSClient++ scripts folder on Windows Server Client

Edit NSC.ini (config file for NSclient++) and add in section [External Scripts]

check_backup=cmd /c echo scripts\check_backup.ps1; exit($LastExitCode) | powershell.exe -command -

Authorize remote scripts execution

In powershell (Run as Admin) execute this command

Set-ExecutionPolicy remotesigned

Restart service NSClient++

On powershell

Restart-Service NSClientpp

Enable feature .NET Framework 

DISM /Online /Enable-Feature /FeatureName:NetFx3



HowToRun on Monitoring

Create a command with check_nrpe like this

$USER1$/custom/check_backup -H $ARG1$




