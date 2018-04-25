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
    
### Install web server and configure

    sudo yum install nginx #To use it as proxy
    vi /etc/nginx/nginx.conf
    
    #Change to:
    location / {
        proxy_pass http://127.0.0.1:8080;
    }    

    sudo sytemctl enable nginx
    sudo systemctl start nginx
    sudo systemctl status nginx
    
    #You can check the site at http://hostname
    
    sudo getenforce
    sudo setenforce 0
    sudo getenforce
    
    sudo systemctl restart nginx #You can check the site at http://hostname
    
    sudo yum install -y setroubleshoot-server selinux-policy-devel
    sudo sepolicy network -t http_port_t
    sudo semanage port -a -t http_port_t -p tcp 8080
    
    sudo setenforce 1
    sudo getenforce
    sudo systemctl restart nginx jenkins
    
    #Check the site at http://hostname
    
    #Add more configuration at /etc/nginx/nginx.conf for the reverse proxy setup, check Running Jenkins behind nginx under Manage Jenkins menu
    
---

## 
    
    
    
    
