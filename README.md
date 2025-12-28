# shitty-cluster
a simple-to-use [ansible](https://docs.ansible.com/projects/ansible/latest/index.html) playbook for setting up your very own [docker swarm](https://docs.docker.com/engine/swarm/) cluster on [debian](https://www.debian.org)-based systems

## usage manual, ADHD edition:
0. install ansible on your machine
1. ensure all of your target hosts have the same user with sudo perms on them and the same password
2. throw all your target hosts into `inventory.yml` according to the provided `inventory.yml.example`
3. run `ansible-playbook prepare.yaml -k` - this will install python3 and python3-apt in raw mode, required for minimal distros that don't have those out of the box
4. run `ansible-playbook setup.yaml -k -v -C` - this will execute the main playbook in check mode with level 1 verbosity, allowing you to see what will be done without actually making any changes. analyze the output and make sure you're okay with what will be done if you're patient enough. if not, skip to step 5
5. run `ansible-playbook setup.yaml -k` - this will execute the main playbook and set up the cluster for you, spitting out some info about it in the very end

## usage manual, boring edition
TBA