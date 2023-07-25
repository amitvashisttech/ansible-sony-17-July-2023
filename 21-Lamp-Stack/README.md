# Ansible mysql_user module is not working the way its expected, hence we need to make change in DB Manually 

```
mysql -u root -p 
```

## Create a WordPress User:
```
CREATE USER 'new_user'@'localhost' IDENTIFIED BY 'password';

GRANT ALL PRIVILEGES ON * . * TO 'new_user'@'localhost';

FLUSH PRIVILEGS;  
```
```
CREATE USER 'wpuser'@'localhost' IDENTIFIED BY 'redhat'; 

GRANT ALL PRIVILEGES ON * . * TO 'wpuser'@'localhost';

FLUSH PRIVILEGS;  
```


## Create a DB For WordPress
```
CREATE DATABASE 'db_name';
``` 
```
CREATE DATABASE 'myWP';
``` 
