## Automated E.L.K. Stack Deployment

The files in this repository were used to configure the network illustrated below.

![AZURE RedTeam_Network](Images/diagram_filename.png)

These files have been tested and used to generate a live E.L.K. deployment on Azure. They can be used to either recreate the entire deployment pictured above, or select portions of the Playbook file may be used to install only certain pieces of it, such as Filebeat.

  [etc/ansible/install-elk.yml](https://github.com/tsommer8/Project_1/blob/dbf31fb2fd08aa86dfa5e6ad5644797d0ea743ab/ansible/.YML%20Scripts/install_elk.yml)
  
This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly secure, in addition to restricting access to the network.
- What aspect of security do load balancers protect?
  - Availiability, one of the three main objectives of the cybersecurity triad is protected with a load balancer. 
- What is the advantage of a jump box?
  - The JumpBox with in this network serves a two fold purpose. The first allows us to deploy software to the multiple web VM's in a single move using Docker/Ansible, instead of having to install software to them individually. Second, it allows for more restriced access to the network given our network security group (NSG) rules.

Integrating an E.L.K. server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
- What does Filebeat watch for?
  - Filebeat is used for monitering log files on the web VM's that are hosting the DVWA. Then sends those logs to Elasticsearch/Logstash for later reveiw     by a cybersecurity specialist.
- What does Metricbeat record?
  - Metricbeat beat works in a simialar fashion to Filebeat, however it is more statistic driven providing various different types of graphs to give the       cybersecuirty specialist a better snap shot of what is going on with the web VM's.

The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| JumpBox  | Gateway  | 10.0.0.4   | Linux (Ubuntu)   |
| Web-1    | DVWA     | 10.0.0.5   | Linux (Ubuntu)   |
| Web-2    | DVWA     | 10.0.0.6   | Linux (Ubuntu)   |
| ELK-Stack| ELK      | 10.1.0.4   | Linux (Ubuntu)   |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JumpBox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP address:
- 58.215.90.36

Machines within the network can only be accessed by SSH protocol via port 22.
-The JumpBox was the only machinge that had access to the E.L.K. VM, its IP address is 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 58.215.90.36         |
| Web-1    | No                  | 10.0.0.4             |
| Web-2    | No                  | 10.0.0.4             |
| ELK-Stack| No                  | 10.0.0.4             |

### E.L.K. Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because
deploying automation simultaneously across multiple machine reduce the risk of error in setting them up individually/manually.

The playbook implements the following tasks:
- Install  
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

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
