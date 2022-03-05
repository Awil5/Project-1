## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![](https://github.com/Awil5/Project-1/blob/main/Diagram/Project%201%20-%20Diagram.jpg)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

----

### Playbook Files

This document contains the following details:
- [Description of the Topology](https://github.com/Awil5/Project-1#description-of-the-topology)
- [Access Policies](https://github.com/Awil5/Project-1#access-policies)
- [ELK Configuration](https://github.com/Awil5/Project-1#elk-configuration)
  - [Beats in Use](https://github.com/Awil5/Project-1/edit/main/README.md#beats-in-use)
  - [Machines Being Monitored]
- [How to Use the Ansible Build](https://github.com/Awil5/Project-1/edit/main/README.md#using-the-playbook)


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.

- **What aspect of security do load balancers protect? What is the advantage of a jump box?**

Load Balancer's help mitigate attacks such as DDoS, the advantage of a JumpBox is to provide a more secure enviornment by only allowing Administrator tasks to be conducted from this internal resource.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the Web activity and system logs.

- Filebeat monitors system log data
- Metricbeat gathers metrics and sends them to specific outputs.

The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| ElkServer| Kibana   | 10.1.0.4   | Linux            |           
| Web 1    | DVWA     | 10.0.0.6   | Linux            |
| Web 2    | DVWA     | 10.0.0.7   | Linux            |

----

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

**Only the host machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:**

- The JumpBox is only accessible from my current public IP.

Machines within the network can only be accessed by my JumpBox.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 10.0.0.4             |
| ELK      | NO                  | 10.1.0.4             |
| Web 1    | NO                  | 10.0.0.6             |
| Web 2    | NO                  | 10.0.0.7             |

----

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it allows different systems to communicate through configuration and easy to develop and access.

The playbook implements the following tasks:

1. Use apt module to install docker.io,
2. use apt module to install pip3,
3. use pip module to install docker python module,
4. use system control module to use more memory
5. use docker_container module to download and launch a docker elk container and use systemd module to enable service on the root.


The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

Note: Unable to access machines any longer.

----

### Target Machines & Beats

This ELK server is configured to monitor the following machines:

Web 1 10.0.0.6
Web 2 10.0.0.7

We have installed the following Beats on these machines:

Metricbeat and Filebeat

These Beats allow us to collect the following information from each machine:

- Filebeat reviews log files and events and I would expect to see it get sent to Elasticsearch or Logstash for additional analysis.

- Metricbeat watches servers and collects metrics and I would expect to see it send information to Logstash for additional review.

----

### Using the Playbook

In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:

- Copy the host file to enviornment.
- Update the host file to include the correct group and ip addresses.
- Run the playbook, and navigate to Kibana to check that the installation worked as expected.

### Answer the follwing questions

- The yml file in the Host file
- Docker and Elkstack
- Kibana, I no loner have acess to my Azure Portal but it is Kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
