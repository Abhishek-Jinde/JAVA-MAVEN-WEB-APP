JAVA - MAVEN - GITHUB - JENKINS - INTERGRATION PROJECT

Pre-requistes
Step 1 : Create a EC2 Instance and install Jenkins 
  #Install Java before installing Jenkins
  
  sudo apt update
  sudo apt install openjdk-17-jre
  
  #Once JAVA is installed, go ahead and install Jenkins
  
  curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
  echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
  sudo apt-get update
  sudo apt-get install jenkins

Step 2 : Once Jenkins is installed, install Git in Jenkins
  sudo apt-get install git -y

Step 3 : Configure JDK Plugin
  #ssh to jenkins server and run the following command
  sudo apt install openjdk-8-jdk -y
  
  Go to Manage Jenkins => Global Tool Configuration
  Click on Add JDK => uncheck Install automatically option
  
  #In name add below line
  OracleJDK8

  #In JAVA_HOME add below line and save.
  /usr/lib/jvm/java-8-openjdk-amd64

Step 4 : Configure MAVEN Plugin
Go to Manage Jenkins => Global Tool Configuration
Click on Add Maven 

#In the name add below line
Maven 3.6

#Select the MAVEN Version
Maven 3.6.1

Select Apply and save

Step 5 : Create a new Item, give the name and select Free Style Project

Step 6 : Under Source Code Management
  Selct Git and enter the git project URL
  Add credential if the repository is Private

Step 7 : Under "Build Steps"
  Select "Invoke top-level Maven Targets" from drop down
  Select Maven version
  Add goals as "clean package"

Step 8 : Click on Build now

