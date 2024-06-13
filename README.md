# Automated Minecraft Server Deployment on AWS

## Background
### What Will We Do?
- **Provision AWS infrastructure:** Using Terraform, we will create an EC2 instance, configure networking components like VPC and security groups, and ensure that all necessary AWS resources are correctly set up for running a Minecraft server.
- **Configure and manage the Minecraft server:** Once the infrastructure is ready, Ansible will be used to install the Minecraft server, configure its settings, and ensure it's ready for players to connect.

### How Will We Do It?
- **Using Terraform:** We'll write infrastructure-as-code scripts to define and deploy the cloud resources needed.
- **Using Docker and Docker Compose:** Docker will be utilized to containerize the Minecraft server, ensuring consistent environments and easy deployment through Docker Compose.


## Requirements
### Prerequisites
To successfully execute the scripts and deploy the Minecraft server, you will need:
- AWS Account
- Terraform installed on your machine ([Download Terraform](https://www.terraform.io/downloads.html))
- Ansible installed on your machine ([Install Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html))
- AWS CLI installed and configured ([AWS CLI Configuration](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html))

### Credentials and Configuration
- **AWS Credentials:** Ensure that your AWS credentials are configured properly by running `aws configure`. This will set up your access key, secret key, and default region.


## Major Steps
### Diagram of Your Major Steps
![Diagram of Your Major Steps](images/diagram_of_your_major_steps.jpeg)

### Diagram of My Major Steps
![Diagram of My Major Steps](images/diagram_of_my_major_steps.jpeg)


## List of Commands to Run
```bash
# Clone the repository
git clone https://github.com/awhittle2/Minecraft-Server.git
cd Minecraft-Server/

# Enter your AWS account details
```
What you'll need:
- Your AWS Access Key ID
- Your AWS Secret Access Key
- Your AWS Session Token

Where to go to find it:
1. Start your Learner Lab
2. Click `AWS Details`
3. Click `AWS CLI: Show`

```bash
# Replace the underscores with your AWS credentials
export AWS_ACCESS_KEY_ID=___
export AWS_SECRET_ACCESS_KEY=___
export AWS_SESSION_TOKEN=___

# Make sure that main.tf is present
ls

# Initialize the terraform project
terraform init

# Apply the changes
terraform apply

# Wait about 4 minutes for it to create the instance and run the set-up script

# Then, connect to the Minecraft Server using the IP address that prints out

# If you do not know how, please refer to the last section of this README file

# Lastly, to test if it auto-starts on reboot, replace the underscores with the instance ID that also gets printed out, and press enter
aws ec2 reboot-instances --instance-ids i-___
```

## How to Connect to Minecraft Server

### Test the Server Using Nmap
```
nmap -sV -Pn -p T:25565 <instance_public_ip>
```

### Test the Server With Minecraft
1. Open the latest stable version of Minecraft
2. Click on multiplayer
![Minecraft Multiplayer Image](images/minecraft_multiplayer.png)
3. Select __Add Server__
![Minecraft Add Server Image](images/minecraft_add_server.png)
4. Create a name and under **Server Address**, enter the public IPv4 address of your server, then click **Done**.
![Minecraft Server Info Image](images/minecraft_server_info.png)
5. Wait for Minecraft to connect to the server
6. Click on your server and then click **Join Server**
![Minecraft Join Server Image](images/minecraft_join_server.png)
7. Enjoy your very own Minecraft server! Congratulations!!
![Play Minecraft Image](images/minecraft_done.png)