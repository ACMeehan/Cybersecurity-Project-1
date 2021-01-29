# Cybersecurity-Project-1
Automated ELK Stack Deployment
The files in this repository were used to configure the network depicted below.
Update the path with the name of your diagram](Images/diagram_filename.png)
https://drive.google.com/file/d/1AcupukBgxZybD_vIE8gFUJ0TmXvivd6y/view?usp=sharing
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansible file may be used to install only certain pieces of it, such as Filebeat.

https://richmond.bootcampcontent.com/AlisonMeehan/project1/blob/master/Install%20Elk%20Playbook
https://richmond.bootcampcontent.com/AlisonMeehan/project1/blob/master/Hosts.yml
https://richmond.bootcampcontent.com/AlisonMeehan/project1/blob/master/ansible.cfg
https://richmond.bootcampcontent.com/AlisonMeehan/project1/blob/master/filebeat-playbook.yml

This document contains the following details:

Description of the Topologu
Access Policies
ELK Configuration
Beats in Use
Machines Being Monitored
How to Use the Ansible Build

Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly secure, in addition to restricting access to the network.

What aspect of security do load balancers protect? What is the advantage of a jump box?_
Load balancers protect from a ddos attack or something similar. A jump box can connect to several machines and containers while limiting access to one point.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the ¬¬¬log files__ and system metrics.

What does Filebeat watch for?_log files
What does Metricbeat record?_metrics from the OS and services running on a server

The configuration details of each machine may be found below.
Note: Use the Markdown Table Generator to add/remove values from the table.

Name
Function
IP Address
Operating System

Jump Box
Gateway
10.0.0.4
Linux

Elk

10.1.0.5
Linux

Web VM    1
Web
10.0.0.1
Linux

Web VM 2
Web
10.0.0.9
Linux

Web VM 3 2
Web
10.0.0.7
Linux 

Access Policies
The machines on the internal network are not exposed to the public Internet.
Only the Elk___ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

Whitelisted IP addresses:
173.53.109.114

Machines within the network can only be accessed by jumpbox

Which machine did you allow to access your ELK VM? What was its IP address?_
173.53.109.114

A summary of the access policies in place can be found in the table below.

Name
Publicly Accessible
Allowed IP Addresses

Jump Box
Yes/No / 10.0.0.1 10.0.0.2

SSH  / yes /ny
Vnet / yes /Any
AllowAzureLB /yes /any
Deny all inbound  /no/none

Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

What is the main advantage of automating configuration with Ansible?
Ansible will make configuring many containers much faster.

The playbook implements the following tasks:

In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._


- Install docker

- Increase virtual memory

- Download docker

- Launch Docker


The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.
!Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

Target Machines & Beats
This ELK server is configured to monitor the following machines:

List the IP addresses of the machines you are monitoring_
10.0.0.11
10.0.0.7
10.0.0.9
We have installed the following Beats on these machines:
TODO: Specify which Beats you successfully installed

These Beats allow us to collect the following information from each machine:

TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., Winlogbeat collects Windows logs, which we use to track user logon events, etc.


Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
SSH into the control node and follow the steps below:

Copy the filebeat file to /etc/filebeat/filebeat.yml.
Update the metricbeat file to include...
Run the playbook, and navigate to /etc/ansible to check that the installation worked as expected.

Answer the following questions to fill in the blanks:_

Which file is the playbook? Where do you copy it?

Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?
A configuration file (ansible.cfg) and hosts.yml ;
Hosts ;   - name: drop in filebeat.yml
copy:
src: /etc/ansible/files/filebeat-config.yml
dest: /etc/filebeat/filebeat.yml
_Which URL do you navigate to in order to check that the ELK server is running?
http://20.62.82.148:5601/app/kibana


As a Bonus, provide the specific commands the user will need to run to download the playbook, update the files, etc.
