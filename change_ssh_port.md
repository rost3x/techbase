**Modify the following file**       
`/etc/ssh/sshd_config/`     
Uncomment change the line `#Port 22` to your desired port       

**Add the new port number to selinux**      
`semanage port -a -t ssh_port_t -p tcp #PORTNUMBER`     

**Restart systemd service**     
`systemctl restart sshd`        

**Add the new port to the firewall**        
`firewall-cmd --add-port=NEWPORT/tcp --pernament`       

At this point we can remove ssh service from the firewall as it nolonger uses port 22       
`firewall-cmd --remove-service=ssh --pernament`     

`firewall-cmd --reload`     

**Restart systemd service one more time**       
`systemctl restart sshd`