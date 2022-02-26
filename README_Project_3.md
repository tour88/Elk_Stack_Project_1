## Automated ELK Stack Deployment
* put diagram *

The files in this repository were used to configure the network depicted below.
(Images/project_2_diagram.png)
![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

yaml, metricbeats, filebeat playbook, ansible 

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.

What aspect of security do load balancers protect? What is the advantage of a jump box?_
It acts as a reverse preoxy and distributes network traffic across multiple servers. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the network and system security.

What does Filebeat watch for?_ 
A light weight log shipper which is installed as an agent on your servers nd monitors the log files or locations that you spcoifcy.

What does Metricbeat record?_
Metricbeat takes the metrics and statistics that it collectss and ships them to the output that you specify. 

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.7   | Linux            |
| Web 1    |          | 10.0.0.8   | Linux            |
| Web 2    |          | 10.0.0.9   | Linux            |
| Elk Server|         | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the _____ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
IP: 10.0.0.7

Machines within the network can only be accessed by: JumpBoxProvisioner.

Which machine did you allow to access your ELK VM? What was its IP address?_
JumpBoxProvisioner 10.0.0.7

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.7             |
| Web 1    | No                  | 10.0.0.8             |
| Web 2    | No                  | 10.0.0.9             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
What is the main advantage of automating configuration with Ansible?_

Very simple to use and set up.

The playbook implements the following tasks:

In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
*Create a new vNet in Azure in a different region, in the same resource group. 
*Create a new VM in the new vNet
*Add the new VM to the ANsible's hosts file.
*Create ANsible playbook that installs Docker and congfiures an ELK Container.
*Run the playbook to launch the container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:

JumpBoxProvisioner 10.0.0.7
Web 1 10.0.0.8
Web 2 10.0.0.9

We have installed the following Beats on these machines:
Filebeats, Metricbeats.

These Beats allow us to collect the following information from each machine:
Filebeats is for forwarding and centealizing log data. 
Metricbeats is used to collect metrics from the OS and from sergices running on the server. 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._