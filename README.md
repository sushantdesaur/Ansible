# Ansible Guide 


## Command to ping servers from control machine 

```
ansible "host_name or group name" -m ping -i inventory.yaml
```

## Command to manage packages with the yum package manager

### These commands are an example for "httpd" package 

Installing the package with root privilege 

```
ansible "host_name or group name" -m ansible.builtin.yum -a "name=httpd state=present" -i inventory.yaml --become
```

Uninstalling the package with root privilege

```
ansible "host_name or group name" -m ansible.builtin.yum -a "name=httpd state=absent" -i inventory.yaml --become
```

Starting and enabling the httpd service with root privilege  
```
ansible "host_name or group name" -m ansible.builtin.service -a "name=httpd state=started enabled=yes" -i inventory.yaml --become
```

Copying files  
```
ansible "host_name or group name" -m ansible.builtin.copy -a "src=filename.extension dest=/var/www/html/file.extension" -i inventory.yaml --become
```


