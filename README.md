# Cloud-Security-Project

## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![](/Diagram/Cloud-Diagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the yaml file may be used to install only certain pieces of it, such as Filebeat.

  - ![Pentest.yml](Ansible/pentest.yml)

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting traffic to the network.
- _TODO: What aspect of security do load balancers protect? Prevents access to the back end of the server from public What is the advantage of a jump box? It masks the internal IP addresses

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the configuration files and system system logs.
- _TODO: What does Filebeat watch for?_ Sudo commands, ssh logins and linux logins
- _TODO: What does Metricbeat record?_ Monitors CPU, RAM and Network usage

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.14   | Linux            |
| Web-1     |   Webserver       |    10.0.0.5        |          Linux        |
| Web-2     |   Webserver       |     10.0.0.6       |         Linux         |
| ELK-VM    |   SIEM        |        10.2.0.4    |          Linux        |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JumpBox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: My Personal IP Address
- _TODO: Add whitelisted IP addresses_

Machines within the network can only be accessed by The JumpBox.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | My Personal IP    |
| Web-1      NO                  | 10.0.0.14                     |
| Web-2         |  NO                   |  10.0.0.14                    |
| Elk-VM         |  NO                   |  10.0.0.14                    |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it's time efficient and allows us manage multiple machines at same time.
- _TODO: What is the main advantage of automating configuration with Ansible?_

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ... install docker
- ... install Python Module
- ... increase system memory
- ... install ELK Container



### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_
Web-1 10.0.0.5
Web-2 10.0.0.6

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
Metric Beats
File Beats

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
Answer: File Beats: for monitoring  SSH, sudo commands and linux account logins
Metric Beats: CPU Usage, Memory and Network Usage
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the etc/ansible/file beat.yml file to etc/ansible/files folder.
- Update the filebeat config file to include the IP address of the ELK Server
- Run the playbook, and navigate to /etc folder to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it? /etc/ansible_folder
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_ The Host File
- _Which URL do you navigate to in order to check that the ELK server is running? The ELK Server's Public IP address

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._ curl , nano, and ansible playbook