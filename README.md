# ansible-restart-idrac
Asnsible playbook to restart idrac from within an ubuntu machine, when idrac is not respoding elsewhere. 
Requires: 
- SSH access to server 
- installed idrac service module

Uses: 
/opt/dell/srvadmin/iSM/bin/Invoke-iDRACHardReset

it does not affect user settings. 


Details: 

This script will first use the command module to log in to the server using the SSH user and hostname specified in the Ansible inventory. The result of this login attempt is stored in the ssh_result variable.

If the login attempt was successful, the script will then use the command module to run the command /opt/dell/srvadmin/iSM/bin/Invoke-iDRACHardReset -f to restart the iDRAC.

After restarting the iDRAC, the script will use the pause module to wait for x minutes to allow the iDRAC to come back online.

Finally, the script will use the command module to log out of the server.

To use this script, you would save it as a file with a .yml extension, such as restart_idrac.yml. You would then run the script using the following command:

ansible-playbook restart_idrac.yml
