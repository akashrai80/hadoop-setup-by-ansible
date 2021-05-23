# hadoop-setup-by-ansible
this two playbooks setup the name node nad tha data node of hadoop cluster 

## note:
 before running the playbook, you must have a ansible setup on your controller node where you run the playbook.
 You should also have follwoing softwares available in your current folder where you are working in.
 1. jdk-8u171-linux-x64.rpm
 2. hadoop-1.2.1-1.x86_64.rpm
 
 (you can get this s/w on internet)
 
 ## ansible setup:
 1. pip install ansible
 
 This library also depend on one more software calld **sshpass**. To download it go to internet search for epel release , on the first site you will get a command , run this command in your command prompt of linux. it will configure the yum with almost all the software available on internet.
 
 2. yum install sshpass
 3. create any text file -> **a.txt**
 4. **a.txt** 
    
    [namenode]
    
    -> <IP of Target Node to be set as name node>  **ansible_user** = <user name>  **ansible_ssh_pass** = <password> **ansible_connection** = <ssh for linux/winrm for windows>
   
    [datanode]
    
    -> <IP of Target Node to be set as data node>  **ansible_user** = <user name>  **ansible_ssh_pass** = <password> **ansible_connection** = <ssh for linux/winrm for windows>
  
  5. mkdir /etc/ansible
  6. i /etc/ansible/ansible.cfg
    
     [defaults]
  
     inventory = <full path of the file **a.txt**>
  
     host_key_checking = False
     

## setup name node:
  1. download all files from hadoop nn folder
  2. run the hadoopnamenode.yml

