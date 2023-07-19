  257  cd 05-Modules/
  258  ls
  259  ansible-doc -l 
  260  ansible-doc apt 
  261  ansinle-doc -s service
  262  export TERM=xterm
  263  vim ansible.cfg
  264  ls
  265  ansible web -m apt -a "name=apache2 state=present"
  266  ansible web -m service -a "name=apache2 state=started"
  267  systemctl status apache2
  268  ansible 172.31.0.100 -m service -a "name=apache2 state=stopped"
  269  systemctl status apache2
  270  ansible 172.31.0.100 -m service -a "name=apache2 state=started"
  271  systemctl status apache2
  272  systemctl status ufw
  273  ansible web -m service -a "name=ufw state=stopped"
  274  ansible 172.31.0.100 -m service -a "name=apache2 state=stopped"
 
