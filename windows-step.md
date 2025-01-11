%%%%%%%%%%%%%%%%%%%%%%% windows as ansible target machine (Here we define the steps to use a windows machine as target)
 
** Check if openssh is installed

 Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH*' 
** install openssh server

Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0

** check sshd daemon
Get-Service sshd

** start sshd daemon

 Start-Service sshd
** enable daemon
Set-Service -Name sshd -StartupType 'Automatic'