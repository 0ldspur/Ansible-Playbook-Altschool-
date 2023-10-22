
Overview
This documentation outlines the process of automating the provisioning of two Ubuntu-based servers, "Master" and "Slave," using Vagrant and Ansible. The project objective is to deploy a LAMP (Linux, Apache, MySQL, PHP) stack on the "Master" server and use Ansible to execute a bash script on the "Slave" server. Additionally, an Ansible playbook is used to create a cron job on the "Slave" server to check its uptime every day at 12 AM.

Repository Structure
The GitHub repository is organized as follows:

Repository Root
│
├── ansible.cfg
├── Inventory
├── site.yaml
├── Files
│   ├── laravel-slave.sh
├── master-slave
│   ├── Vagrantfile
│
├── Laravel.sh
├── README.md

The repository is made up of;
- Laravel
- Lampstack
- Ansible 
- Master and Slave

Ansible Playbook
- ansible.cfg
- Inventory
- site.yaml

- Files:
    - laravel-slave.sh

master-slace file:
Laravel.sh:

Conditions
    - .env
    - mysql
    -ansible config file


How I Set Up My Project
I organized my project in a way that makes it simple to automate server tasks and deployments. Here's how I structured everything:

ansible.cfg: I used this to customize how Ansible works for my project. Think of it like the project's control center. It's where I fine-tuned Ansible to suit our needs, such as telling it where to find the inventory and setting up SSH options.

Inventory: This file is kind of like the guest list for Ansible. It contains the names or IP addresses of the servers we want Ansible to manage. So, this is where we list our "Master" and "Slave" servers.

site.yaml: I created this as the project's to-do list for Ansible. It's like a checklist of tasks that I wanted Ansible to carry out on our servers. These tasks could be things like installing software, configuring services, and running scripts.

Files (Directory): This is like our storage space for any extra files or scripts we need for the project. For instance, I kept the laravel-slave.sh script here, which we intended to use on the "Slave" server.

master-slave (Directory): In this directory, I set up the virtual machines using the Vagrantfile. It's as if I had a workshop for building and managing these virtual servers. This file specifies details like the operating system, how much memory each VM gets, and how they connect to the network.

Laravel.sh: I created this as our recipe for setting up a Laravel project on the "Master" server. It's like a step-by-step guide for our server, telling it how to install Laravel, configure everything, and deploy our application.

Usage Instructions:

Follow these steps to provision the "Master" and "Slave" servers and set up the LAMP stack:
    Clone the repository

    Configure the .env and MySQL settings as needed for your Laravel application. These configurations will depend on your specific Laravel project requirements.

    Configure the Ansible inventory in the Inventory file. Specify the IP addresses or hostnames of your "Master" and "Slave" servers.

    Modify the site.yaml playbook to suit your deployment needs, such as installing specific packages, configuring Apache and MySQL, and deploying your Laravel application.

    Deploy the "Master" server with the LAMP stack using Vagrant:

    After the "Master" server is provisioned, deploy your Laravel application using the Laravel.sh script:

    Deploy the "Slave" server using Vagrant:

    Execute the laravel-slave.sh script on the "Slave" server using Ansible. This script may contain specific tasks that you want to run on the "Slave" server:

    Configure a daily cron job to check uptime on the "Slave" server:
    
    Update your site.yaml playbook to include a task for creating the cron job. Ensure that it runs the laravel-slave.sh script to check uptime daily at 12 AM.
    
    Save your changes to the playbook and re-run Ansible to apply the cron job to the "Slave" server:

Screenshots

https://drive.google.com/file/d/19fDUlrIPXnOWhBB0UcpqLOQdyPg7U_SJ/view?usp=share_link

Contributing
Feel free to contribute to this project by opening issues or submitting pull requests. We welcome any improvements or suggestions.

License
This project is licensed under the MIT License.

