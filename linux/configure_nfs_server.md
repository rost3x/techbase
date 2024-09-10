**Create a directory you want to share**        
**Edit export file**        
`vim /etc/exports`      
`/directory *(rw,sync)`     

**Install nfs-utils and enable systemd service**        
`dnf install -y nfs-utils`            
`systemctl enable --now nfs-server`     

**Enable nfs service on the firewall**      
`firewall-cmd --add-service=nfs --permanent`        
`firewall-cmd --add-service=rpc-bind --permanent`       
`firewall-cmd --add-service=mountd --permanent`     


