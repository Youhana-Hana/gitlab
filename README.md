### GitLab area
Scripts in here are mainly set to configure the GitLab VM. 

### current features
* check connecttivity to GitLab VM
* ensure a list of packages are installed through RPM from repos
* download gitlab-ce  rpm and install it
* Reconfigure and start gitlab server
* Add users


### running the main playbook

ansible-playbook ~/gitlab/main.yml \
-i ~/git-repos/pcf-ansible/inventory \
-e ansible_ssh_user=user \
-e ansible_ssh_pass=PASSWORD \
-e ansible_sudo_pass=PASSWORD \ 
-e target_hosts=target_hosts

### create admin token

Login as root and update root password. Create an api token and use it to add users, through running below playbook.

### installation
pip install pyapi-gitlab (http://docs.ansible.com/ansible/latest/list_of_source_control_modules.html)

### running the configure playbook
This to add automation group and users to gotlab server. All users added with inital password 'password'
ansible-playbook ~/gitlab/configure.yml \
-i ~/git-repos/pcf-ansible/inventory \
-e ansible_ssh_user=user \
-e ansible_ssh_pass=PASSWORD \
-e ansible_sudo_pass=PASSWORD \ 
-e target_hosts=target_hosts   \ 
-e url= git lab url
-e token= administrator api token
