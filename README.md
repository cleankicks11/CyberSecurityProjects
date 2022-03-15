## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

CyberSecurityProjects/Diagrams/Untitled Diagram.drawio

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the cyberSecurityProjects/Ansible/ file may be used to install only certain pieces of it, such as Filebeat.

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the Damn Vulnerable Web Application.

Load balancing ensures that the application will be highly avaiiable, in addition to restricting Flooding to the network.
-Aspect of security which load balancers protect are availability and redundancy. I have used a jump box to control the access to the network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system services.
-Filebeat watches for ghtweight way to forward and centralize logs and files behavior across your aggregated logs.
-Metricbeat Collects metrics from your systems and services. From CPU to memory, Redis to NGINX, and much more


| Name       | Function  | IP Address | Operating System |
|------------|-----------|------------|------------------|
| Jump Box   | Gateway   | 10.0.0.8   | Linux            |
| Web-1      |Webserver  | 10.0.0.7   | Linux            |
| Web-2      |Webserver  | 10.0.0.6   | Linux            |
| ELK-Machine|Monitoring | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump-Box-Provioner machine can accept connections from the Internet. Access to this machine is only allowed from whitelisted following IP addresses.

Machines within the network can only be accessed by Jump-box-provisioner.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  | 167.160.91.13        |


### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
-The main advantage of automating configuration with Ansible simultaneous deployment with out human error

The playbook implements the following tasks:
- Configure Server memory
- Install Docker
- Download image 
- Install Python3-pip
- Enable and start ELK services

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web-1
- Web-2

We have installed the following Beats on these machines:
- Filebeats
- MetricBeats

These Beats allow us to collect the following information from each machine:
-Filebeat watches for ghtweight way to forward and centralize logs and files behavior across your aggregated logs.
-Metricbeat Collects metrics from your systems and services. From CPU to memory, Redis to NGINX, and much more

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the Filebeat-config.yml file to filebeat.yml.
- Update the Filebeat-config.yml file to include...
- Run the playbook, and navigate to ELK-Machine to check that the installation worked as expected.

- Filebeat-playbook.yml
- To make Ansible run the playbook on a specific machine edit /etc/Ansible/hosts edit [webservers] lines to include IP address and ansible_python_interpreter=/usr/bin/python3
- Navigate to  http://[your.ELK-VM.External.IP]:5601/app/kibana in order to check that the ELK server is running.

Run commands to download playbook:
git repo clone cleankicks11/CyberSecurityProjects
