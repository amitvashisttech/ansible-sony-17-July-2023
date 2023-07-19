288  cd 06-Facts/
  289  ls
  290  ansible web -m ping
  291  ansible-doc setup
  292  ansible 172.31.0.100 -m setup
  293  ansible 172.31.0.100 -m setup -a "filter=ansible_os_family"
  294  ansible 172.31.0.100 -m setup -a "filter=ansible_processor"
  295  ansible 172.31.0.100 -m setup -a "filter=ansible_nodename"
  296  ansible 172.31.0.100 -m setup -a "filter=ansible_fqdn"
  297  ansible web -m setup -a "filter=ansible_fqdn"
  298  ansible-doc  setup
  299  ansible 172.31.0.100 -m setup
  300  ansible web -m setup -a "filter=ansible_user_shell"
  301  ansible 172.31.0.100 -m setup --tree ./setup
  302  ls
  303  cd setup/
  304  ls
  305  cd ..
  306  ls
  307  rm -rf setup/
  308  ansible all -m setup --tree ./setup
  309  ls
  310  cd setup/
  311  ls
  312  cat 172.31.0.100
  313  ls
  314  python -m json.tool 172.31.0.100
  315  python -m json.tool 172.31.0.100 | grep -i master
  316  ls
