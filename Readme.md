
# Quickly obtain bigip_device_facts from a BIG-IP.

## modify host file 

## build the container

docker build -t facts .

## run the container interactively

docker run -it -v $(pwd):/ansible/playbooks facts:latest

## Once in the container, run the playbook using the following command.

ansible-playbook facts.yml -i hosts

It will ask you for username, password, and what data you want. Username and password can be any read only user on the big-ip. For the data entity, you can find all your choices [here](https://docs.ansible.com/ansible/latest/modules/bigip_device_info_module.html#bigip-device-info-module). 

You can only choose one because of the way the playbook is written. Also, it is not recommended to select 'all' as it might time out.

For example,  

What data do you want?: ltm-pools