# ansible

Description

This code provides a simple Ansible playbook for creating and uninstalling an Nginx web server on EC2 instances. It utilizes Ansible's declarative syntax to specify the desired state of the servers and perform the necessary tasks.

Prerequisites

Ansible: Make sure you have Ansible installed on your local machine.
Usage

Create Nginx Web Server
Update the hosts field in the playbook to specify the target EC2 instances where you want to create the Nginx web server.
Run the following command to execute the playbook and create the Nginx web server:
Copy code
ansible-playbook create_nginx.yml
This will install the latest version of Nginx and start the Nginx service on the specified EC2 instances.

Uninstall Nginx Web Server
Update the hosts field in the playbook to specify the target EC2 instances from which you want to uninstall Nginx.
Run the following command to execute the playbook and uninstall Nginx:
Copy code
ansible-playbook uninstall_nginx.yml
This will remove the Nginx package from the specified EC2 instances and stop the Nginx service.

Playbook Structure

The playbook is divided into two separate plays, each with its own purpose: creating and uninstalling the Nginx web server.

Create Nginx Web Server
Name: create nginx web server
Hosts: Specify the target EC2 instances where you want to create the Nginx web server.
Become: Set to true to escalate privileges using sudo.
Tasks:
Name: install nginx server
Apt: Installs the latest version of the Nginx package using the apt package manager.
Name: nginx
State: latest
Name: start nginx server
Service: Starts the Nginx service.
Name: nginx
State: started
Uninstall Nginx Web Server
Name: uninstall nginx web server
Hosts: Specify the target EC2 instances from which you want to uninstall Nginx.
Become: Set to true to escalate privileges using sudo.
Tasks:
Name: uninstall nginx server
Apt: Removes the Nginx package from the EC2 instances using the apt package manager.
Name: nginx
State: absent
Name: stop nginx server
Service: Stops the Nginx service.
Name: nginx
State: stopped
Customization

EC2 Hosts: Update the hosts field in the playbook to specify the target EC2 instances.
Nginx Version: If you want to install a specific version of Nginx, modify the apt task by specifying the desired version.
Additional Configuration: If you need to customize the Nginx configuration, you can add additional tasks or modify existing tasks in the playbook to suit your requirements.
Limitations

Assumes EC2 instances are already provisioned and accessible.
Assumes the playbook is executed with the necessary permissions to install and uninstall packages and start/stop services on the target EC2 instances.
Contributing

Contributions to this project are welcome. If you find any issues or have suggestions for improvements, please open a GitHub issue or submit a pull request.

