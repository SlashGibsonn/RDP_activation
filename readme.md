# RDP Windows 11 Pro Server Activation via Terminal

## Steps

1. Activate RDP:
   ```sh
   reg add "HKLM\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections /t REG_DWORD /d 0 /f
   ```

2. Ensure Windows Firewall allows RDP connection
   ```sh
   Enable-NetFirewallRule -DisplayGroup "Remote Desktop"
   ```
   if not works, use Powershell instead
   ```sh
   powershell
   ```
   ```sh
   Enable-NetFirewallRule -DisplayGroup "Remote Desktop"
   ```

3. Check RDP Status, if its value equals to zero thus RDP connection is allowed 
   ```sh
   net localgroup "Remote Desktop Users" nama_user /add
   ```

4. Restart RDP Service (if necessary)
   ```sh
   Restart-Service TermService
   ```
