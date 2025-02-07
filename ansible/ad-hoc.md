#### A small collection of the adhoc commands

`ansible "server var" -m ping`      

`ansible "server var" -m command -a uptime`     

    - Adding a `-m command -a` allows to execute arbitrary commands with the command module.     

`ansible "server var" -a uptime`        

    - Since the command module is the default module in Ansible you can omit it.        

`ansible "server var" -a "ps -aux"`      

    - If the command has spaces, add double quotes so shell can pass the entire string as a single argument.        


