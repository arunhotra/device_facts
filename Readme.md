
# Quickly obtain bigip_device_facts from a host.

## modify host file 
## modify facts file to change to what data you need 

## build the container

### docker build -t facts .

## run the container interactively

### docker run -it -v $(pwd):/ansible/playbooks facts:latest

## Once in the container, run the playbook using the following command.

### ansible-playbook facts.yml -i hosts

It will ask you for username, password, and what data you want. Username and password can be any read only user on the big-ip. For the data entity, you have the following choices (case sensitive). You can only choose one because of the way the playbook is written. Also, it is not recommended to select 'all' as it might time out.

all
monitors
profiles
asm-policy-stats
asm-policies
asm-server-technologies
asm-signature-sets
client-ssl-profiles
devices
device-groups
external-monitors
fasthttp-profiles
fastl4-profiles
gateway-icmp-monitors
gtm-pools
gtm-servers
gtm-wide-ips
gtm-a-pools
gtm-a-wide-ips
gtm-aaaa-pools
gtm-aaaa-wide-ips
gtm-cname-pools
gtm-cname-wide-ips
gtm-mx-pools
gtm-mx-wide-ips
gtm-naptr-pools
gtm-naptr-wide-ips
gtm-srv-pools
gtm-srv-wide-ips
http-monitors
https-monitors
http-profiles
iapp-services
iapplx-packages
icmp-monitors
interfaces
internal-data-groups
irules
ltm-pools
ltm-policies
nodes
oneconnect-profiles
partitions
provision-info
self-ips
server-ssl-profiles
software-volumes
software-images
software-hotfixes
ssl-certs
ssl-keys
system-db
system-info
tcp-monitors
tcp-half-open-monitors
tcp-profiles
traffic-groups
trunks
udp-profiles
users
vcmp-guests
virtual-addresses
virtual-servers
vlans

For example,

What is your username?: readOnly
What is your password?: 
What data do you want?: ltm-pools