# In the following demo will be setting up 3 Node Environment ( 1 ACS & 2 Remote Server ) 

## Login to master node & clone the repo 

### 1. Open the cmder toll from desktop

### 2. Change the directory to "devops-lab/vagrant-setup/devops"
```
cd devops-lab/vagrant-setup/devops
```
### 3. Check the VM status 
```
vagrant status 
```
```
master                    running (virtualbox)
worker1                   running (virtualbox)
worker2                   running (virtualbox)
```

### 4. Bring up the VMs
```
vagrant up master
```

### 5. Login / connect to VM
```
vagrant ssh master
```
```
sudo su - 
```

### 6. Install Ansible on Debain Node
```
apt-get update 
apt-get install -y ansible 
```

### 7. Check Ansible Installation 
```
ansible --version 
```
