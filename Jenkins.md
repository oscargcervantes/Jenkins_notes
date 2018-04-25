---

# Jenkins

---

## Installation and configuration

### Get the latest package

    #CentOS 7
    
    sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins-ci.org/redhat/jenkins.repo
    sudo rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key
    sudo yum update
    sudo yum install jenkins
    
### Install Java

    sudo yum install java-1.8.0-openjdk #Check firewall rules
    
### Enable service

    sudo systemctl enable jenkins
    sudo systemctl start jenkins
    sudo systemctl status jenkins
    
### 
