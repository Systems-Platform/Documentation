### STEPS TO CONFIGURE A ANSIBLE SERVER

## Note: Pre-requisite python2

Launch an RHEL8 EC2 instance

Switch to root and update the yum repository

    yum update -y  

Install python2 by yum install python2

Check the version by python2 --version

    <image src="images/Checkpython.jpg"/>

Install Ansible by pip2 install ansible
'''
Configure the default path of ansible in /etc/ by creating a directory ansible
   
    cd /etc/ --> mkdir ansible
		  
Create a directory roles and files naming as ansible.cfg and hosts

    cd /ansible/ --> mkdir roles
	   
	touch ansible.cfg hosts
	
'''						
Check the version of ansible as shown below

    <image src="images/Checkansibleconf.jpg"/>
'''
Create a user named as ansadmin and give root permissions (in both controller and target server)
'''

    useradd ansadmin
	
	passwd ansadmin
	
Give root permissions to the user 

	visudo 
	
	<image src="images/Addingroot.jpg"/>
	
'''
Enable password less authentication (in both controller and target server)

    vi /etc/.ssh/sshd_config
'''

'''	 
Restart the sshd service
         
	service sshd restart

'''		   

Switch to the user ansadmin

'''

Generate ssh key by ssh-keygen

'''

Go to the path /home/ansadmin/authorized_keys/id_rsa.pub

Copy the ssh key to the target servers 

'''  
    ssh-copy-id <target-server ip address>
		  
	<image src="images/ssh-copy.jpg"/>
'''		  
Add the ip address of target servers in the hosts

    vi /etc/ansible/hosts
		   
	<image src="images/Addhosts.jpg"/>
		   
Check the connection by 
'''         
	ansible all -m ping
		  
	<image src="images/Checkping.jpg"/>
'''		  	   
Create a directory playbooks and write the playbooks and run by 
      
    ansible-playbook <playbook name>
		 




		   
		   