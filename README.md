# kubertest
1.AWS Instance Created

2.Docker Installed

sudo yum remove docker \
                 docker-client \
                 docker-client-latest \
                 docker-common \
                 docker-latest \
                 docker-latest-logrotate \
                 docker-logrotate \
                 docker-selinux \
                 docker-engine-selinux \
                 docker-engine

sudo yum install -y yum-utils \
 device-mapper-persistent-data \
 lvm2

sudo yum-config-manager \
   --add-repo \
   https://download.docker.com/linux/centos/docker-ce.repo

sudo yum install docker-ce -y

sudo groupadd docker

sudo usermod -aG docker $(whoami)

sudo service docker start

sudo service docker enable

Rancher Installed for kubernetes
docker run -d --restart=unless-stopped -p 443:443 -v /host/rancher:/var/lib/rancher rancher/rancher:latest

Tomcat Installed

sudo yum install tomcat

sudo vi /usr/share/tomcat/conf/tomcat.conf


JAVA_OPTS="-Djava.security.egd=file:/dev/./urandom -Djava.awt.headless=true -Xmx512m -XX:MaxPermSize=256m -XX:+UseConcMarkSweepGC"
sudo yum install tomcat-webapps tomcat-admin-webapps 
sudo systemctl start tomcat


sudo systemctl enable tomcat

sudo systemctl status tomcat



Jenkins Installed
sudo yum install java-1.8.0-openjdk-devel
curl --silent --location http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo | sudo tee /etc/yum.repos.d/jenkins.repo

sudo rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key

sudo yum install jenkins

sudo systemctl start jenkins

Changing Port Number to 8081
vi /etc/sysconfig/jenkins
JENKINS_PORT="8080"
Replace by 8081
   systemctl restart jenkins
   systemctl status jenkins
    cat /var/lib/jenkins/secrets/initialAdminPassword

NGINX INSTALL AND RUN IN CENTOS 7

sudo yum install yum-utils
      vi /etc/yum.repos.d/nginx.repo
     sudo yum-config-manager --enable nginx-mainline
     sudo yum install nginx
     syestemctl start nginx
     systemctl start nginx.service
     systemctl status nginx.service
   systemctl enable nginx.service
