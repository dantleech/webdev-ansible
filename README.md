Voralberg WebDev Ansible Demo
=============================

Install vagrant and ansible:

````bash
$ apt-get install vagrant ansible
````

Start the virtual machines:

````bash
$ vagrant up
````

Generate the SSH configuration (warning: this will OVERWRITE existing configuration):

````bash
$ vagrant ssh-config > ~/.ssh/config
````

Note that we use a private DHCP network, you may have to do this:

````bash
$ VBoxManage dhcpserver remove --netname HostInterfaceNetworking-vboxnet0
````

Run the ansible playbook:

```bash
$ ansible-playbook playbook.yml -i hosts
````

Get the IP address of the loadbalancer:

````bash
$ ssh loadbalancer /sbin/ifconfig | grep eth1 -A1
````

Visit the load balancer in your browser:

````
http://<ip address of load balancer>
````

Or check the HaProxy statistics:

````
http://<ip address of load balancer>:9000/haproxy_stats
````
