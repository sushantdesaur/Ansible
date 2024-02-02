# Ansible Guide 


## Command to ping servers from control machine 

```
ansible "host_name or group name" -m ping -i inventory.yaml
```

## Command to manage packages with the yum package manager

### This command is an example for "httpd" package 

Installing the package with root privilege 

```
ansible "host_name or group name" -m ansible.builtin.yum -a "name=httpd state=present" -i inventory.yaml --become
```

Uninstalling the package with root privilege

```
ansible "host_name or group name" -m ansible.builtin.yum -a "name=httpd state=absent" -i inventory.yaml --become
```