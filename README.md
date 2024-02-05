# Ansible Guide 


## Ad-hoc commands

Command to ping servers from control machine 

```
ansible "host_name or group name" -m ping -i inventory.yaml
```

Installing the "httpd" package with the yum package manager using root privilege 

```
ansible "host_name or group name" -m ansible.builtin.yum -a "name=httpd state=present" -i inventory.yaml --become
```

Uninstalling the package with the yum package manager using root privilege (--become)  

```
ansible "host_name or group name" -m ansible.builtin.yum -a "name=httpd state=absent" -i inventory.yaml --become
```

Starting and enabling the httpd service with root privilege (--become)  

```
ansible "host_name or group name" -m ansible.builtin.service -a "name=httpd state=started enabled=yes" -i inventory.yaml --become
```

Copying files  

```
ansible "host_name or group name" -m ansible.builtin.copy -a "src=filename.extension dest=/var/www/html/file.extension" -i inventory.yaml --become
```

Running a playbook

```
ansible-playbook -i inventory.yaml web-db.yaml
```

Checking for syntax error in the playbook

```
ansible-playbook -i inventory.yaml web-db.yaml --syntax-check
```

Doing a dry run before actually applying the changes 

```
ansible-playbook -i inventory.yaml web-db.yaml -C
```
Gathers facts about remote hosts

```
ansible -m setup host_name
```


