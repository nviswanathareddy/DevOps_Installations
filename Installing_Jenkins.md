# Installing Jenkins on Debian Packages

Updating the Packages
```bash
sudo apt-get update && sudo apt-get upgrade
```

This is the Debian package repository of Jenkins to automate installation and upgrade. To use this repository, first add the key to your system
```bash
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
```

Then add the following entry in your /etc/apt/sources.list:
```bash
sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ >> /etc/apt/sources.list'
```

Update your local package index, then finally installing Jenkins
```bash
sudo apt-get update && sudo apt-get install jenkins
```

Checking the Jenkins status and starting if not
```bash
sudo service status jenkins
sudo service start jenkins
sudo service stop jenkins
```

# Installing Jenkins on Redhat Packages

Updating the packages
```bash
yum update
```

To use this repository, run the following command
```bash
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
```

If you've previously imported the key from Jenkins, the rpm --import will fail because you already have a key. Please ignore that and move on
```bash
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
```

Update your local package index, then finally installing Jenkins
```bash
yum update && yum install jenkins
```