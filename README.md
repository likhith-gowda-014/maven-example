Experiment 1:
sudo apt update
sudo apt install openjdk-17-jdk -y
sudo apt install maven -y
wget https://services.gradle.org/distributions/gradle-8.14-bin.zip -P /tmp
sudo unzip -d /opt/gradle /tmp/gradle-8.14-bin.zip
gedit ~/.bashrc
export GRADLE_HOME=/opt/gradle/gradle-8.14
export PATH=${GRADLE_HOME}/bin:${PATH}
source ~/.bashrc

Experiment 2:
For Maven:
mvn archetype:generate -DgroupId=com.example -DartifactId=MyMavenApp -
DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
sudo snap install tree
gedit pom.xml
gedit src/main/java/com/example/App.java
gedit src/test/java/com/example/AppTest.java
mvn clean install
java -cp target/classes com.example.App

Experiment 3:
gradle init --type java-application --dsl groovy –overwrite
gradle init --type java-application --dsl kotlin –overwrite (for kotlin)
gedit app/build.gradle or gedit app/build.gradle.kts (for kotlin)
gradle build
gradle run

Experiment 4:
mvn archetype:generate -DgroupId=com.example -DartifactId=HelloMaven -
DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
gradle init –type java-application
gedit build.gradle
gradle build
gradlew run

Experiment 5:
sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
/etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt install jenkins -y
sudo systemctl start jenkins
sudo systemctl enable jenkins
sudo systemctl status jenkins
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
Experiment 7:
sudo apt update
sudo apt upgrade -y
sudo apt install ansible -y
gedit hosts.ini
gedit setup.yml
sudo ansible-playbook -i hosts.ini setup.yml
Experiment 8:
ansible-playbook -i hosts.ini deploy.yml
or
ansible-playbook -i /path/to/hosts.ini /path/to/deploy.yml
gedit deploy.yml
