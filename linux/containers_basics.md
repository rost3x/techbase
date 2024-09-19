**Search for images**       
`podman search imagename`       
`podman pull imagename` - To pull the image to your server (without running it)     

**Run a container image**       
`podman run -d --name=whatevername IMAGEID`      
The following options can be added:     
`-e` - Set environment variable. For example mariaDB requires you to create a ROOT_PASSWORD, therefore, it can be used as the following:        
`podman run -d --name=whatevername -e ROOT_PASSWORD=password IMAGENAME/IMAGEID`           
You can also publish port, which is required with majority of images. For example nginx requires port 80 to work hence the following can be done:       
`podman run -d --name=whatevername -p 8080:80/tcp IMAGENAME/IMAGEID`        
[host_port]:[container_port]/protocol       

**Run container as systemd service**        
`loginctl enable-linger username`       

Create the following directory in the user's home folder `.config/systemd/user`.        
Navigate to that direcotry and type in the following whilst the container is running `podman generate systemd --name typeinaname --files`       
Reload systemd `systemctl daemon-reload`, and try to run the container as a service `systemctl --user enable --now container-name.service`      

