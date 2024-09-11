**Download autofs**     
`dnf install -y autofs`     

Create a folder you want to use autofs on.      

`mkdir /users`      
/users - is an NFS folder       

**Change master file**      

`vim /etc/auto.master`      
Add the following line to the bottom:       
`/home/users    /etc/auto.users`        
/home/users - a local directory that you would like link to the nfs     
/etc/auto.users - autofs config file that will be created in the next steps     

**Create and modify users config file**     

`vim /etc/auto.users`       
Add the line:       
`anna   -rw,sync    localhost:/users/anna`      

anna - is taking a directory from /home/users/anna and tells autofs to map nfs directory located at localhost(or nfs server ip):/users/anna     

You can also use wildcards:     
`linda  -rw,sync    localhost:/users/&`     
