## Installation
Key generation:

    ssh-keygen -t dsa -f .ssh

Start VMs:

    vagrant up

Cat all lsb-release entries

    ansible all -a "cat /etc/lsb-release" -i local.inv --private-key .ssh -u bear

Tired of specifying private key? Use

    ssh-add .ssh

Tail the syslog on the root node

    ansible root -a "sudo tail -n 10 /var/log/syslog" -i local.inv -u bear

## Regular operations
Install common packages:

     ansible-playbook books/common.yml -i local.inv
