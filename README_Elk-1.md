## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

  - install-elk.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network. Load balancers defends against DDoS attacks by shifting attack traffic to another public server. A jump box is a secure computer that admins must connect to securly before launching any administrative task.



Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
-Filebeat keeps logs of everything happening on a system.
- Metricbeat keeps track of how well the system is preforming.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
|Elk-Server|          | 10.1.0.4   | Linux            |
| Web-1    |          | 10.0.0.7   | Linux            |
| Web-2    |          | 10.0.0.6   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JumpBox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- My IP

Machines within the network can only be accessed by the Jump Box.
- Public:20.24.216.77
 Private:10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  |                      |
|Elk-Server| No                  |                      |
| Web-1    | Yes                 |                      |
| Web-2    | Yes                 |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- The task is preformed quickly and there is no room for human error making it efficent. Using Ansible also allows for changes to be made on all machines at once.

The playbook implements the following tasks:
- Install docker.io
- Install pip3 for python
- Download and launch docker elk container
- Enable service docker on boot

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web-1:10.0.0.7
  Web-2:10.0.0.6

We have installed the following Beats on these machines:
- filebeat and metricbeat

These Beats allow us to collect the following information from each machine:
- System logs and system metrics. System logs are any event that occurs on the entire system. System metrics are how well the machine is working and collects data such as CPU, memory and network statistics.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the playbook.yml file to JumpBox.
- Update the Config file to include the ip of Elk-Server
- Run the playbook, and navigate to Elk-ip:5601/apps/kibana to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- install-elk.yml in the slack
- Update the config file 
- Elk-ip:5601/apps/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._