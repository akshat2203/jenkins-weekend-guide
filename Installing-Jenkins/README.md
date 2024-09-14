# Jenkins Installation Guide (Debian/Ubuntu)

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
