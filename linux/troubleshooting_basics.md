### A critical server/service is down and you need to fix it. What are
### the first steps you need to take?	

1. Recognize the issue and gather all the posible data.		
2. Create an action plan.	
3. Test possible solutions based on the data.	
4. If the issue is still present, research more data and go back to the
3rd step.

### Troubleshooting system packages	

> Replace nginx with whatever service you want to investigate.				
```sh
which nginx
```	
The above will display which executable file it is and it's location.

```sh
rpm -qf /usr/sbin/nginx
```	
This will show the package that installed the binary.		

```sh
rpm -qlc nginx
rpm -qld nginx
```	

Those two will display either configuration files associated with the
service or the documentation files.		


### Logs	

The default logs location on the servers is in		
`/var/logs/`	

### TCPDUMP	

Tcpdump allows you to capture and analyze network traffic on your
system. Some system may have it pre-installed however, on RHEL it can be
installed via	
	
```sh
sudo dnf install tcpdump
```	

Tcpdump needs elevated permissions, therefore, `sudo` must be used.	

To display network interfaces on the system you can type	

```sh
sudo tcpdump -D
```
