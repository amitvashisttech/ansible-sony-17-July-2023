 335  ansible-playbook site.yaml
  336  ansible-playbook site.yaml --tags "webserver"
  337  ansible-playbook site.yaml --tags "common"
  338  cat hosts
  339  vim playbooks/server-common.yaml
  340  ansible-playbook site.yaml --tags "common"
  341  ansible-playbook site.yaml --tags "common" --limit web
  342  cat hosts
  343  ansible-playbook site.yaml --tags "common" --limit ansible
  344  ansible-playbook site.yaml --tags "common" --limit db
  345  ansible-playbook site.yaml --tags "common" --limit 'db:ansible'
  346  ansible-playbook site.yaml --tags "common" --limit 'prod:&web'
  347  ansible-playbook site.yaml --tags "common" --limit 'prod:&web:!ansible'
  348  ansible-playbook site.yaml --tags "common" --limit 172.31.0.102
