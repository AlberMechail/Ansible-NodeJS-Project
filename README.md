# Ansible-NodeJS-Project
NodeJS Application Deployment using Ansible Playbook
Ansible-NodeJS-Project
This project automates the deployment of a Node.js application using Ansible. It sets up the necessary environment, installs dependencies, configures system services, and ensures the application is running and accessible.

📁 Project Structure
![image](https://github.com/user-attachments/assets/4f6a4374-fdda-4e28-a9f6-0c90c971d4b0)

Ansible-NodeJS-Project/
├── app/                  # Node.js application source code
│   ├── app.js
│   └── package.json
├── inventory             # Ansible inventory file listing target hosts
├── playbook.yaml         # Main Ansible playbook for deployment
└── README.md             # Project documentation

🚀 Features
Installs Node.js and npm on the target server
Creates a dedicated system user for running the application
Sets up the application directory with appropriate permissions
Copies application source code to the target server
Installs application dependencies using npm
Configures the application as a systemd service for easy management
Ensures the application starts on boot and is actively running
Configures the firewall to allow traffic on the application's port

🛠️ Prerequisites
Ansible installed on the control machine
Access to the target server with appropriate SSH permissions
Target server running CentOS 9
EPEL repository enabled on the target server (for npm installation)

📦 Application Details
The sample Node.js application is a simple Express server defined in app.js with the following package.json:

{
  "name": "examplenodeapp",
  "description": "Example Express Node.js app.",
  "author": "Jeff Geerling <geerlingguy@mac.com>",
  "dependencies": {
    "express": "4.x"
  },
  "engine": "node >= 0.10.6"
}

⚙️ Usage
Clone the Repository

git clone https://github.com/AlberMechail/Ansible-NodeJS-Project.git
cd Ansible-NodeJS-Project

Configure Inventory
Edit the inventory file to include your target server's IP address or hostname:

[nodejs_servers]
192.168.152.100 ansible_user=root

Run the Playbook
Execute the Ansible playbook to deploy the application:

ansible-playbook -i inventory playbook.yaml
