# jenkins_linux 2.277.3
You will need to pre-install a supported version of Java:
2.164 (2019-02) and newer: Java 8 or Java 11
2.54 (2017-04) and newer: Java 8
1.612 (2015-05) and newer: Java 7

安装java
rpm -qa | grep jdk
yum remove 删除其他版本jdk
yum search openjdk
yum install java-11-openjdk
java -version

安装jenkins
wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
vi /etc/yum.repos.d/jenkins.repo
[jenkins]
name=Jenkins-stable
baseurl=https://mirrors.huaweicloud.com/jenkins/redhat-stable
gpgcheck=1

rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key

yum install jenkins

vi /etc/sysconfig/jenkins
JENKINS_HOME="/home/jenkins"


Start Jenkins
systemctl start jenkins
systemctl status jenkins

日志：
tailf /var/log/jenkins/jenkins.log

初始化密码：
cat /var/lib/jenkins/secrets/initialAdminPassword

http://127.0.0.1:8080
