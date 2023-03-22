# ansible-tutorial

# why ansible?

1) to automate
2) faster
3) intelligence that one command can run on any platform of os without worrying 




Difference between ansible and cheff/puppet
in asnible-worker node no need to install agents

but in cheff and puppet we must have to install agents in the worker node 

Ansible key points

ansible is push based architecture

cheff and puppet pull based architecture


Ansible features

1)agentless connection using ssh

  1)linux server--> ssh
  2)windows server--> winrm

2) ansible built by python and python functionality

3) we write ansible playbook yaml format 

4) follow push based architecture

Push Based vs Pull based

pull based --> tools like chef and puppet are pull based, the agents of worker node periodically checks for configuration information from  master 

push based --> ansible will only push the configuration in target server, so no need check or wait from target


why we need to write palybook in yaml why not python???

why because if write in python then you have to install python in all of the target servers but if you write yaml then no need to install yaml in target 

/etc/ansible/hosts --> inventory file

there are two inventory file 

1) static 
2) dynamic 

