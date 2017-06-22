pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh '#!/bin/sh'
                echo 'curl -s "https://get.sdkman.io" | bash'
                sh 'java -version'
                sh 'puppet --version'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                echo 'sudo mkdir /opt/gradle'
                echo 'sudo cd /home/vinaymachamraj/Downloads'
                echo 'sudo wget https://services.gradle.org/distributions/gradle-4.0-bin.zip'
                sh 'sudo unzip -d /opt/gradle -o gradle-4.0-bin.zip'
                sh 'sudo ls /opt/gradle/gradle-4.0'
                sh 'export PATH=$PATH:/opt/gradle/gradle-4.0/bin'
                sh '/opt/gradle/gradle-4.0/bin/gradle -v'
                sh 'cd ~'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                echo 'sudo mkdir /opt/maven'
                sh 'sudo cd /home/vinaymachamraj/Downloads'
                echo 'sudo wget http://mirror.olnevhost.net/pub/apache/maven/maven-3/3.5.0/binaries/apache-maven-3.5.0-bin.tar.gz'
                sh 'sudo tar -xvf apache-maven-3.5.0-bin.tar.gz -C /opt/maven'
                sh 'sudo ls /opt/maven/apache-maven-3.5.0/bin'
                sh 'export PATH=$PATH:/opt/maven/apache-maven-3.5.0/bin'
                echo 'sudo wget http://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo'
                echo 'sudo yum check'
                echo 'sudo yum install -y apache-maven'
                sh '/opt/maven/apache-maven-3.5.0/bin/mvn -v'
            }
        }
    }
}
