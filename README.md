# Usecase 1
Description: Create & Launch a AWS EC2 instance with Ansible and deploy the sample nodejs application to the instance and access the service form outside the world.

1.Create EC2 Instance through Ansible.
    - pre-requisites
        - Aws key, Secret and Keypair to connect.
       -  Security group with port 80 & 22 opened to our network.
       Code in the create-machine.yaml
       
2.Running the playbook:    ansible-playbook create-machine.yaml
    
3. get the ip address of the machine created and add in the Hosts file Ref: Hosts
 
4. Created sample node js application to deploy through script
 Sampleapp.sh
 
5. Playbook for deploying the Application File name: deploy.yaml
 
6. Run the playbook with Hosts file - if not mentioned it will take the default hosts file
     ansible-playbook -i Hosts deploy.yaml
  
# Usecase 2
Description: Install the Tomcat server in the server and deploy the springboot jar file from the nexus repositery to the      tomcat and restart the tomcat after deployment and access the service from the machine public Ip with port 8080.
  
1. Install the tomcat in the ec2 instance.
   Mention the Port to run , Check for the apache is already there, and related user group is there are not if not create        the group and assaign the installed tomcat group newly created and start the tomcat instance .
     ansible-playbook -i Hosts install_tomcat.yaml
     
2. Deploy the jar from nexus and restart the tomcat.
     ansible-playbook -i Hosts deploy_to_tomcat.yaml
    
    
  
  
