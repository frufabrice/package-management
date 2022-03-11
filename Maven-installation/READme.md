#  **<span style="color:green">Landmark Technologies, Ontario, Canada.</span>**
### **<span style="color:green">Contacts: +1437 215 2483<br> WebSite : <http://mylandmarktech.com/></span>**
### **Email: mylandmarktech@gmail.com**



## Apache Maven Installation And Setup In AWS EC2 Redhat Instnace.
##### Prerequisite
+ AWS Acccount.
+ Create Redhat EC2 T2.medium Instnace with 4GB of RAM.
+ Create Security Group and open Required ports.
   + 22 ..etc
+ Attach Security Group to EC2 Instance.
+ Install java openJDK 1.8+AA

### Install Java JDK 1.8+  and other softares (GIT, wget and tree)

cd /opt
yum install wget nano tree unzip git-all -y
yum install java-11-openjdk-devel java-1.8.0-openjdk-devel -y
java -version
git --version

#2. Install Maven.sh
#------------------

#Step1) Download the Maven Software

wget https://dlcdn.apache.org/maven/maven-3/3.8.4/binaries/apache-maven-3.8.4-bin.zip

unzip apache-maven-3.8.4-bin.zip
rm -rf apache-maven-3.8.4-bin.zip
mv apache-maven-3.8.4/ maven

#Step3) Set Environmental Variable  -  For Specific User
----------------------
#vi ~/.bash_profile
echo "export M2_HOME=/opt/maven" >>  ~/.bash_profile
echo "export PATH=$PATH:$M2_HOME/bin" >> ~/.bash_profile


#Step3b) Set Environmental Variable  For All Users
---------------------- 
echo "export M2_HOME=/opt/maven" >>  /etc/profile
echo "export PATH=$PATH:$M2_HOME/bin" >> /etc/profile

#step4) Activate the maven home and mvn by running the below scripts
source /etc/profile

#Step5) Check the Maven version

source ~/.bash_profile
mvn -version
