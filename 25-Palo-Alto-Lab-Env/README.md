# Palo Alto Lab Env. 

## We are using VMWare Workstation 7 Pro Trail Version to run Palo Alto Appliences

## In VMWare Workstation, we have the following instances:

1. Ansible
2. PA-Ex ( PaloAlto Firewall EXI )
3. Pano  ( PaloAlto Panoroma EXI)

## Login to Ansible Node: 

1. Open Cmder / GitClient / Putty / Powershell 

UserName : vagrant 
Password : vagrant

```
ssh vagrant@192.168.249.128
```

2. Become a Super User
```
sudo su - 
```

3. Install Ansible 
```
apt-get update ; apt-get install ansible -y 
```

4. Install PAN Python Packages
```
apt-get install python3-pip -y 
pip3 install pan-python
```

5. Other Palo Also PAN Dependency
```
pip3 install pandevice==0.13
```

6. Install PaloAlto Ansible Modules / Collection from Galaxy.
```
ansible-galaxy collection install paloaltonetworks.panos
```
