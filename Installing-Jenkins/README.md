# Jenkins Installation Guide (Debian/Ubuntu)

## Installation of Java

Jenkins requires Java to run, yet not all Linux distributions include Java by default. Additionally, not all Java versions are compatible with Jenkins.

Update the Debian apt repositories, install OpenJDK 17, and check the installation with the commands:

```bash
sudo apt update
sudo apt install fontconfig openjdk-17-jre
```

This guide will help you install Jenkins on a Debian-based system (such as Ubuntu). Follow the steps below to get Jenkins up and running!

---

## Step 1: Add Jenkins GPG Key

Download and install the Jenkins GPG key to verify the packages:

```bash
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
```

## Step 2: Add Jenkins Repository

Add the Jenkins package repository to your system’s sources list:

```bash
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/" | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
```

## Step 3: Update Package Index

Update the package index to include the new Jenkins repository:

```bash
sudo apt-get update
```

## Step 4: Install Jenkins

Finally, install Jenkins using the following command:

```bash
sudo apt-get install jenkins
```

## Step 5: Start and Enable Jenkins 

Start and Enable the Jenkins service:

```bash
sudo systemctl start jenkins
sudo systemctl enable jenkins
```

## Step 6: Access Jenkins

Jenkins runs on port 8080 by default. Open your browser and navigate to:

## Local Machine:

Access Jenkins using:

```bash
http://localhost:8080
```

## Remote Server:

If you’re running Jenkins on a remote server, replace localhost with your server’s IP address or domain name. For example:

```bash
http://<your-server-ip>:8080
```

## AWS EC2:

If you’re using AWS EC2, you can access Jenkins via the public IP address of your instance:

```bash
http://<ec2-public-ip>:8080
```

## To retrieve the initial admin password for Jenkins setup, use:

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```


