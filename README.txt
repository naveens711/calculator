======================
Maven build Life Cycle:
======================
Each of these build lifecycles is defined by a different list of build phases, wherein a build phase represents a stage in the lifecycle.
    validate - validate the project is correct and all necessary information is available
    compile - compile the source code of the project
    test - test the compiled source code using a suitable unit testing framework. These tests should not require the code be packaged or deployed
    package - take the compiled code and package it in its distributable format, such as a JAR.
    verify - run any checks on results of integration tests to ensure quality criteria are met
    install - install the package into the local repository, for use as a dependency in other projects locally
    deploy - done in the build environment, copies the final package to the remote repository for sharing with other developers and projects.===============

===============================
Seting up jenkin user password:
===============================
1- sudo su
2- passwd jenkins
3- set the <password>
4- exit
5- su - jenkins 
6- supply <password>

=======================================
Setup to setup Eclipse in Ubuntu Lab:-
------------------------------------------
1- Open browser: search for eclipse dwonload
2- Open terminal
      uname -a
      output> x86_64 ~ 64 bit OS
3- Download url https://www.eclipse.org/downloads/download.php?file=/oomph/epp/2020-06/R/eclipse-inst-linux64.tar.gz  [copy to broser and hit download button]
4- In terminal [ruuning the eclipse]
    4.1  cd Downloads
    4.2  ls -lrt
         > eclipse-inst-linux64.tar.gz [last file in rsult of above command]
    4.3 tar -xvf eclipse-inst-linux64.tar.gz [extract the tar file]
    4.4 cd eclipse-installer
    4.5 ./eclipse-inst  [Choose Eclispe IDE Java Developers. it will open a GUI based installation window, just fallow the default conf. It will also launch the eclipse. Close Welcome window.]
    4.6 Check already install instance location: /home/ubuntu/eclipse/java-2020-06/ [File Manager ] [if this location does not exist, then we have to install]
           > double click on `eclipse` file 
           > ./eclipse [to run via command line]
    4.7 Choose workspace directory [go for default one]
5- Creating a Maven project in eclipse
      5.1 Top left corner
            > File
                  > New
                        > other
                              > Maven
                                    > Maven Project
                                          > [click on Next]
                                                > Choose default working location
                                                      > New Maven Project
                                                            > Select ArcheType
                                                                  > Catalog: internal
                                                                  > GroupId: org.apache.mavne.archtypes
                                                                  > artifactId: maven-archtype-quickstart
                                                                  > version: 1.1
                                                                        > [Next]
                                                                              > Project details
                                                                                    > Group Id: com.simplilearn.cicd
                                                                                    > Artifact Id: jfrog-demo
                                                                                          > [Finish]                                                                                     
====================================================================================================================================
===================================
 Setup to install JFrog Artifactory
===================================
1- Search for: JFrog Artifactory Install 
[https://jfrog.com/artifactoray/free-trial/?utm_source=google&utm_medium=cpc&utm_campaign={campaign}&gclid=EAIaIQobChMI9t3n7Kv56gIVQSUrCh3qcQhdEAAYASABEgJC5PD_BwE]

2- Download link: https://api.bintray.com/content/jfrog/artifactory-pro/org/artifactory/pro/jfrog-artifactory-pro/$latest/jfrog-artifactory-pro-$latest-linux.tar.gz?bt_package=jfrog-artifactory-pro
3- cd Downloads
[All cmd run in terminal]
4- tar -xvf jfrog-artifactory-pro-7.6.3-linux.tar.gz 
5- cd artifactory-pro-7.6.3
6- cd app/bin
7- sudo ./installService.sh 
      output> 
            ************ SUCCESS ****************
            Installation of Artifactory completed

            Start Artifactory with:
            > systemctl start artifactory.service

            Check Artifactory status with:
            > systemctl status artifactory.service
8- Run Jfrog service:
      systemctl start artifactory.service
9- Check Service status:
      sudo systemctl status artifactory.service
      output>   artifactory.service - Artifactory service
               Loaded: loaded (/lib/systemd/system/artifactory.service; enabled; vendor pres
               Active: active (running) since Sat 2020-08-01 06:21:27 UTC; 31s ago
               Process: 28839 ExecStart=/home/ubuntu/Downloads/artifactory-pro-7.6.3/app/bin/
               Main PID: 30809 (java)
                Tasks: 0
               Memory: 120.0K
                  CPU: 2.467s
               CGroup: /system.slice/artifactory.service
                       ‣ 30809 /home/ubuntu/Downloads/artifactory-pro-7.6.3/app/third-party/
10- Open JFrog UI
      http://localhost:8081 [copy in broser and hit]
11- UI login
      username: admin
      password: password
12- Rest the admin password as 12345678 [use simple one for testing]
13 - License Key
cHJvZHVjdHM6CiAgYXJ0aWZhY3Rvcnk6CiAgICBwcm9kdWN0OiBaWGh3YVhKbGN6b2dNakF5TUMw
d09DMHpNVlF3TmpvMU5Ub3hPUzR3TXpSYUNtbGtPaUF4Tm1WbE1qbGxOQzAzWmpka0xUUXlNMk10
T0dZeE1DMWpOelk1WWpaaU56aG1NREVLYjNkdVpYSTZJSE5wYlhCc2FXeGxZWEp1Q25CeWIzQmxj
blJwWlhNNklIdDlDbk5wWjI1aGRIVnlaVG9nYm5Wc2JBcDBjbWxoYkRvZ2RISjFaUXAwZVhCbE9p
QlVVa2xCVEFwMllXeHBaRVp5YjIwNklESXdNakF0TURndE1ERlVNRFk2TlRVNk1Ua3VNRE0wV2dv
PQogICAgc2lnbmF0dXJlOiBHSm5FYXEwNUFhMFNYVDBFbFBQU2hKTjlBMDhWQzNaQlNyekd2WGhC
SkVXeW52aVo1UnpLRlpyNGJmY2ZxZ2ZWc2FzNXZhb3hKeTkrK2hoTFc5dG9MNW1Ea2gvMHc0Z3Nh
ZDJwbXhsMnRHMGhiV1lNdFA4aCs2VE9XRHQrSGZKaDRLVGtNMG1STmI5N2o4S3hCS0F2RWhvZWdV
eklzakdpMEk2dy9rS0FvMXRlOFI2NnFZbFo2R3NXanV1ZEZDWlA0VmdoMjgzOXhoRXZ3ZkgrTmVw
V1pOYlh6Wm15VHZsVmZmQzVYTlROM3Nzb2c5RElTd2FNNnloajhVRjN3eHFxKzZ6LzdYWFBPNXkz
T2FNYURuaUJlUW1wbEVDb3FrMXBWOTVOb2wyVFo2dkFIR05YNFhlaXFmeEFReXNQQXF1VTJzdkw4
aG0zM3ZNaGs2azdTYzVRMmc9PQp2ZXJzaW9uOiAxCg==

14- Skip `base url setting` 

15- Skip `proxy configuration`

16- Create Repository, choose -> `maven` [Click on Finish]

=================================
JFrog and Maven Integration Steps
=================================
1- Top right conrner -> `Set me up` button. Please click on that
2- Choose Tool as -> `maven`
3- Choose credential -> `admin`
4- Click on `Generate Maven settings`
5- Click on `Generate Settings`
6- Click on `generate snippet` -> It will download the settings.xml file in /home/ubuntu/Downloads/ directory
7- Open terminal
      7.1 cd Downloads
      7.2 open settings.xml file and update the JFrog's admin password in it.
            <servers>
                <server>
                  <username>admin</username>
                  <password>12345678</password>
                  <id>central</id>
                </server>
                <server>
                  <username>admin</username>
                  <password>12345678</password>
                  <id>snapshots</id>
                </server>
            </servers>

      7.3 sudo cp settings.xml /var/lib/jenkins/.m2/
      7.4 sudo chgrp jenkins /var/lib/jenkins/.m2/settings.xml
      7.5 sudo chown jenkins /var/lib/jenkins/.m2/settings.xml
======================================================
Setup the Artifactory plugin in project's pom.xml file 
======================================================
1- Add the below section inside the <project> xml tag:
<distributionManagement>
    <repository>
     <id>central</id>
     <name>libs-release</name>
     <url>http://localhost:8081/artifactory/libs-release</url>
    </repository>
    <snapshotRepository>
     <id>snapshots</id>
     <name>libs-snapshot</name>
     <url>http://localhost:8081/artifactory/libs-snapshot</url>
    </snapshotRepository>
  </distributionManagement>
  
  =======
  Setup and test Artifactory Server connectivity
  =============================================
  1- Open Jenkins UI
  2- Go to Manage jenkin
  3- Go to Configure System
  4- JFrog Artifactory section
      4.1 name: JFrog
      4.2 Aritfactory Server: http://localhostL:8081/artifactory
      4.3 Default cridential
            4.3.1 username: admin
            4.3.2 password: 123456
                  [Test connection hit]
      
 =================
  Setup Sonar qube
  =================
  1. Go to this page: https://docs.sonarqube.org/latest/setup/get-started-2-minutes/
  2. Download form here: https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-7.8.zip
      In Terminal:
      2.1 unzip sonarqube-7.8.zip
      2.2 cd /home/ubuntu/Downloads/sonarqube-7.8/bin/linux-x86-64
      2.3 ./sonar.sh console
  3. Go to browser: http://localhost:9000
  4. Login: username- admin
            password- admin
  5. Generate Token: Analyze "com.simplilearn:calculator": 41da3cb9c67b35100c99fee9e89d97a28e18b1a8
  6. Fallow the configuration setup, shown in UI
  7. Add the below profile in settings.xml
       <profile>
            <id>sonar</id>
            <activation>
                <activeByDefault>true</activeByDefault>
            </activation>
            <properties>
                <sonar.host.url>
                  http://localhost:9000
                </sonar.host.url>
            </properties>
        </profile>
  8. Add Plugins in porject's pom.xml inside the <project> xml tag:
   <build>
    <pluginManagement>
      <plugins>
        <plugin>
          <groupId>org.apache.maven.plugins</groupId>
          <artifactId>maven-compiler-plugin</artifactId>
          <version>3.8.1</version>
        </plugin>
        <plugin>
          <groupId>org.sonarsource.scanner.maven</groupId>
          <artifactId>sonar-maven-plugin</artifactId>
          <version>3.6.0.1398</version>
        </plugin>
        <plugin>
          <groupId>org.jacoco</groupId>
          <artifactId>jacoco-maven-plugin</artifactId>
          <version>0.8.4</version>
        </plugin>
      </plugins>
    </pluginManagement>
  </build>

  <profiles>
    <profile>
      <id>coverage</id>
      <activation>
        <activeByDefault>true</activeByDefault>
      </activation>
      <build>
        <plugins>
          <plugin>
            <groupId>org.jacoco</groupId>
            <artifactId>jacoco-maven-plugin</artifactId>
            <executions>
              <execution>
                <id>prepare-agent</id>
                <goals>
                  <goal>prepare-agent</goal>
                </goals>
              </execution>
              <execution>
                <id>report</id>
                <goals>
                  <goal>report</goal>
                </goals>
              </execution>
            </executions>
          </plugin>
        </plugins>
      </build>
    </profile>
  </profiles>   
  
 
 9. mvn clean verify sonar:sonar
 10. If above goal successfully run, then it will produce code analysis report URLs. 
 
 
 ========================
 Setup Web Server: Tomcat
 ========================
 1- Download: http://apachemirror.wuchna.com/tomcat/tomcat-8/v8.5.57/bin/apache-tomcat-8.5.57.tar.gz
 2- cd Downloads
 3- tar -xvf apache-tomcat-8.5.57.tar.gz
 4- cd apache-tomcat-8.5.57
 5- vi conf/server.xml [Change all ports]
      5.1 Replace 8005 to 7005
            <Server port="7005" shutdown="SHUTDOWN">
                  <Listener className="org.apache.catalina.startup.VersionLoggerListener" />
      5.2 Replace 8080 to 7080 and 8443 to 7443
            <Connector port="7080" protocol="HTTP/1.1"
               connectionTimeout="20000"
               redirectPort="7443" />
 6- vi conf/tomcat-users.xml     [add the below roles and admin password in <tomcat-users> xml tag]
        <role rolename="manager-gui"/>
        <role rolename="manager-script"/>
        <role rolename="manager-jmx"/>
        <role rolename="manager-status"/>
        <role rolename="admin-gui"/>
        <role rolename="admin-script"/>
        <user username="admin" password="admin" roles="manager-gui,manager-script,manager-jmx,manager-status,admin-gui,admin-script"/>

 7- Run from terminal  
      7.1 cd /home/ubuntu/Downloads/apache-tomcat-8.5.57 [your untar location]
      7.2 ./bin/startup.sh [to start tomcat]
      7.3 ./bin/shutdown.sh [to stop tomcat]
 8- Go to browser, http://localhost:7080 and hit. 
  
            
===========================
Spring boot Web Application
===========================
1- Download the Spring boot Application: https://github.com/cicdTrainer/spring-boot-demo
2- Clone the project from Git client and packaing (i.e. war file inside target folder) the web application 
    2.1 mkdir /home/ubuntu/web-project
    2.2 cd web-project
    2.3 git clone https://github.com/cicdTrainer/spring-boot-demo.git
    2.4 cd spring-boot-demo/
    2.5 mvn clean package
    2.6 ls target/webappdemo.war
3- Manully deploy web application into web server (tomcat)
    3.1 go to your project directory
    3.2 cd /home/ubuntu/web-project/spring-boot-demo
    3.3 Assuming the tomcat installed on the below location:
        3.3.1 /home/ubuntu/Downloads/apache-tomcat-8.5.57 [webapps is directory where war should deploy]
    3.3 cp target/webappdemo.war /home/ubuntu/Downloads/apache-tomcat-8.5.57/webapps
    3.4 Go to browser
        3.4.1 http://localhost:7080/webappdemo/users/1
                3.4.1.1 Response: {"id":2,"name":"John","nicknames":["jonny"],"age":26,"email":"john@xyz.com"}
                
Continuous Deployment of a war file into a Running Tomcat WebServer via Jenkins Job:
====================================================================================
 1- Go to Manage Plugins
    1.1 Install `Deploy to container plugin`
    1.2 Restart Jenkins
 2- Go to New item [Jenkins Home Page]
    2.1 Choose maven style project
    2.2 SCM
        2.2.1 Git repo
        2.2.2 Reporitory URL: https://github.com/cicdTrainer/spring-boot-demo.git
        2.2.2 Go to `Post-Build-Action`
            2.2.2.1 Choose Deploy war/ear to a container
            2.2.2.2 WAR files: **/*.war
            2.2.2.3 Context path: demo1
            2.2.2.4 Choose 1tomcat 8.x in Containers list box
            2.2.2.5 Tomcat URL: http://localhost:70780 [please modify IP/PORT according to your tomcat location]
            2.2.2.6 Choose Advance
                2.2.2.6.1 /manager/text
            2.2.2.7 Cridential, choose Jenkins provider / Add
                    username: admin
                    password: admin
     2.3 Save
     2.4 Build Job
  3- Go to browser
     3.1 http://localhost:7080/demo1/users/1 [hit]   
=================================================================
Jenkins Pipeline build for a Web Application:
============================================
1- Manually set the pipeline script:
    node {
   stage('Prepare') {
      git 'https://github.com/cicdTrainer/spring-boot-demo.git'
   }
   stage('Compile') {
         sh "'/usr/bin/mvn' -Dmaven.test.failure.ignore clean compile"
   }
}
   
   
   Master/Slave:
   =============
   1- sudo java -jar agent.jar -jnlpUrl http://localhost:8080/computer/test/slave-agent.jnlp -secret fef4874372892b1f433b4356ef2aa5cef09d3dbd52cef61dff314be99448f381 -workDir "/var/jenkins" 
   2- To run a pipeline stage into a slave node:
   pipeline {
  agent any
  stages {
    stage('Stage 1') {
      steps {
        echo "${env.NODE_NAME}"
      }
    }
    stage('Stage 2') {
      agent {label 'test'}
      steps {
          echo "${env.NODE_NAME}"
      }
    }
  }
}
