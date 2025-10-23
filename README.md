# 🐳 Install Docker Engine on Ubuntu

Follow the step-by-step commands to install **Docker Engine** on Ubuntu.

⚠️ **Docker requires Ubuntu 20.04 or newer** (for example: Ubuntu 20.04 LTS, 22.04 LTS, or later).

--- 

## Step-by-Step Installation

### 1️⃣ Update your system

```
sudo apt update # Updates package list
sudo apt upgrade -y # Installs latest update
```
### 2️⃣ Install Prerequisite Packages

**ca-certificates** – *Provides trusted SSL certificates*  
**lsb-release** – *Provides Ubuntu version details*  
**gnupg** – *Handles GPG encryption and verification*  
**curl** – *Command-line tool to download data from URL*  

```
sudo apt install ca-certificates curl gnupg lsb-release -y
```
3️⃣ Add Docker’s official GPG key

This step adds Docker’s official GPG key to your Ubuntu system so that your system can verify the authenticity of Docker packages before installing them.

```
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
 ```
4️⃣ Add Docker Repository to APT Sources

This step tells your Ubuntu system where to find Docker packages, ensures you always install the official, up-to-date Docker packages.
```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

 ```
5️⃣ Update package 

```
sudo apt update
```
6️⃣ Install Docker Engine and related components
```
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
```

###  Verify Docker Installation

**Check Docker version**  

*Verify the installed Docker version to ensure the is working properly.*

```bash
sudo docker --version
```
**or check wheater the Docker engine is running**

```
sudo systemctl status docker
```
