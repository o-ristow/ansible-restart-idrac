# ansible-restart-idrac
Asnsible playbook to restart idrac from within an ubuntu machine, when idrac is not respoding elsewhere. 
Requires: 
- SSH access to server 
- installed idrac service module

Uses: 
/opt/dell/srvadmin/iSM/bin/Invoke-iDRACHardReset

it does not affect user settings. 
