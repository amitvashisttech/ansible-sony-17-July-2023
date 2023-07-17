## Run Ad-hoc command 

### ansible all -i hosts -m ping -u vagrant -k
```
root@master:~/ansible-sony-17-July-2023/01-Inventory# ansible all -i hosts -m ping -u vagrant -k
SSH password:
172.31.0.102 | FAILED! => {
    "msg": "Using a SSH password instead of a key is not possible because Host Key checking is enabled and sshpass does not support this.  Please add this host's fingerprint to your known_hosts file to manage this host."
}
172.31.0.101 | FAILED! => {
    "msg": "Using a SSH password instead of a key is not possible because Host Key checking is enabled and sshpass does not support this.  Please add this host's fingerprint to your known_hosts file to manage this host."
}
root@master:~/ansible-sony-17-July-2023/01-Inventory#

```


### Manully Add the SSH Finger print
```
root@master:~/ansible-sony-17-July-2023/01-Inventory# ssh vagrant@172.31.0.101
The authenticity of host '172.31.0.101 (172.31.0.101)' can't be established.
ECDSA key fingerprint is SHA256:AqvKZ8f98MwzeGfpZ9GDiKggGIdSH0/qDhO0Yw3xFcA.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '172.31.0.101' (ECDSA) to the list of known hosts.
vagrant@172.31.0.101's password:
```

### Check the SSH Know Hosts file
```
root@master:~/ansible-sony-17-July-2023/01-Inventory# cat ~/.ssh/known_hosts
|1|sXacGaCGL1YJTDjPYppUMXUc0Co=|qWW4/c6O13uktpSj0KnxnuiICa8= ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBFQ7y8SM0OhxDUe3EIW5IeBYCB7priTSRDGtBSWqxuLLPVZEsuuBxgxdPLc0EM1F1ALu7nfB7Wm6DSFmevU6jIE=
|1|HZcTmBXg9fdefQ2mp9eQT0gveqc=|F+G8AbAK3nCh5jGNJDiqAHYpJ1Q= ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBBZpMmaGyR/rK+5bciWvtNw3HSxOFfGw5rJyXmZOmn+iEGLz4FTqNw90lDsuSclGzfxiWCtUt3P/R3v/A0V4ruc=
root@master:~/ansible-sony-17-July-2023/01-Inventory#
```

### Let's re-run the ansible 
```
root@master:~/ansible-sony-17-July-2023/01-Inventory# ansible all -i hosts -m ping -u vagrant -k
SSH password:
172.31.0.101 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python"
    },
    "changed": false,
    "ping": "pong"
}
172.31.0.102 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python"
    },
    "changed": false,
    "ping": "pong"
}
root@master:~/ansible-sony-17-July-2023/01-Inventory#
```


