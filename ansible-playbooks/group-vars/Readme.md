////ansible playbook on group variabes//// 


 we use group variables when we have multiple group servers in /etc/ansible/hosts

NOTE: always ansible read variables in this mandatory precedence --> variable in playbooks--> variable files --> hosts --> group -- all.yml 
 // Now we will create group_vars directory under /etc/ansible/hosts

 sudo mkdir /etc/ansible/group_vars

 cd group_vars

 sudo vi webservers.yml
 	javaPackageVersion: java-11-openjdk

 sudo vi appservers.yml
 	javaPackageversion: java-1.8.0-openjdk

 sudo vi all.yml
 	javaPackageversion: java-1.8.0-openjdk                   // this is for localhost which is not in anygroup

// now we will create a playbook

vi installjava.yml

---
hosts: all 
become: true
tasks: 
 -name: install java
  yum: name="{{javapackageversion}}""
... 


////Ansible playbook on host variables//////

// create a directory as host-vars in /etc/ansible/host_vars

 sudo mkdir /etc/ansible/host_vars

 sudo vi /etc/ansible/host_vars/192.168.0.1.yml
 	javapackageversion: java-11-openjdk

// add this 192.168.0.1 ip in any of the group server and run it then it will install the java version which is mentioned in host_vars directory but not the java version in which this ip is installed it will ignore and will not instal

 RUN: ansible-playbook installjava.yml

