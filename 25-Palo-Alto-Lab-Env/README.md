# Palo Alto Lab Env. 

## We are using VMWare Workstation 7 Pro Trail Version to run Palo Alto Appliences

## In VMWare Workstation, we have the following instances:

### 1. Ansible
### 2. PA-Ex ( PaloAlto Firewall EXI )
### 3. Pano  ( PaloAlto Panoroma EXI)

## Login to Ansible Node: 

### 1. Open Cmder / GitClient / Putty / Powershell 

UserName : vagrant 
Password : vagrant

```
ssh vagrant@192.168.249.128
```

### 2. Become a Super User
```
sudo su - 
```

### 3. Install Ansible 
```
apt-get update ; apt-get install ansible -y 
```

### 4. Install PAN Python Packages
```
apt-get install python3-pip -y 
pip3 install pan-python
```

### 5. Other Palo Also PAN Dependency
```
pip3 install pandevice==0.13
```

### 6. Install PaloAlto Ansible Modules / Collection from Galaxy.
```
ansible-galaxy collection install paloaltonetworks.panos
```





## Login to PaloAlto VM - Click on PA-EX VM in VMware Workstation

### 1. Login
```
Username: admin 
Password: Pass@word12345
```

### 2. Check the System Info & IP Address of the Firewall
```
show system info
```

### 3. Configure the Static IP Address
```
configure

set deviceconfig system type static

set deviceconfig system ip-address 192.168.249.210 netmask 255.255.255.0 
default-gateway 192.168.249.254 dns-setting servers primary 8.8.8.8

commit
```

### 4. Now take a duplicate session in cmder & login to firewall.
```
ping -c2 ipaddress_of_pa_firewall
ssh admin@ipaddress_of_pa_firewall
```


## First Ansible PlayBook Exec: 

### 1. Genrate the API key from firewall to Ansible Auth. 
```
curl -k -X POST 'https://firewall-IP/api/?type=keygen&user=admin&password=Pass@word12345'
```
### 2. Update the keys in Group_Vars
```
cat group_vars/palo.yml 
```
```
palo_provider:
  api_key: XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
  ip_address: "{{ ansible_host }}"
```  


