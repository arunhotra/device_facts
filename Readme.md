
# Easy BIG-IP device facts.

## Purpose

This repo provides a very rapid way of getting a fact from a BIG-IP using the bigip_device_facts module. This can be useful in the lab when you want to know a specific fact about BIG-IP. I have also leveraged it while troubleshooting playbooks. Customers use the bigip_device_facts module quite a bit to check for facts and base their playbook decisions on that. So this could be useful while trying to deconstruct customer playbooks.

## Pre-req's

Docker

## Steps

* ### clone the repo

* ### modify hosts file to point to the IP of your BIG-IP

* ### build and run the container

``` docker-compose run facts```

* ### Once in the container, run the playbook using the following command.

``` ansible-playbook facts.yml -i hosts ```

It will ask you for username, password, and what data you want. Username and password can be any read only user on the big-ip. For the data entity, you can find all your choices [here](https://docs.ansible.com/ansible/latest/modules/bigip_device_info_module.html#bigip-device-info-module). 

You can only choose one because of the way the playbook is written. Also, it is not recommended to select 'all' as it might time out.

For example,  

What data do you want?: ltm-pools