
1.dbbackup
after gitclone run below command
change directory name 3s1 to dbbackup
mv 3s1 dbbackup

2.dbbackup.yml

vi dbbackup.yml
- hosts: all
  gather_facts: False
  vars_files:
    - dbbackup/defaults/main.yml
  roles:
    - role: dbbackup
3.vi inventory

localhost  ansible_connection=local
or 
 [ncp-marina-prod-1]
ncp-marina-prod-1 ansible_ssh_host=147.182.189.217 ansible_ssh_user=root ansible_ssh_private_key_file=~/.ssh/id_rsa host_private_ip=10.136.248.71
B.Nagalakshmi@jawed-mac common % 

4.ansible-playbook -i inventory dbbackup.yml







