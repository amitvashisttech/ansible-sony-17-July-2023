 659  mkdir 22-Introduction-to-Vault
  660  cd 22-Introduction-to-Vault/
  661  ls
  662  echo "Hello World.ls" > encrypt_me.txt
  663  echo "Hello World" > encrypt_me.txt
  664  ls
  665  cat encrypt_me.txt
  666  ansible-vault encrypt encrypt_me.txt
  667  cat encrypt_me.txt
  668  file encrypt_me.txt
  669  ansible-vault view encrypt_me.txt
  670  ansible-vault edit encrypt_me.txt
  671  cat encrypt_me.txt
  672  ansible-vault view encrypt_me.txt
  673  s
  674  ls
  675  cp -rf encrypt_me.txt decrypt_me.txt
  676  ls
  677  cat decrypt_me.txt
  678  ansible-vault decrypt encrypt_me.txt
  679  cat decrypt_me.txt
  680  cat encrypt_me.txt
  681  mv encrypt_me.txt decrypt_me-1.txt
  682  ls
  683  mv decrypt_me.txt encrypt_me.txt
  684  mv decrypt_me-1.txt decrypt_me.txt
