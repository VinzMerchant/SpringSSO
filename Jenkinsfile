pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh '#!/bin/sh'
                echo 'wget --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u131-b11/d54c1d3a095b4ff2b6607d096fa80163/jdk-8u131-linux-x64.tar.gz'
                echo 'sudo rpm -ivh /var/lib/jenkins/workspace/SpringSSO_master-V5TU6FK5PZXYQGWOC5VYBAKHEBB3N5R4BBHSUY7UCTEN7G6JOBCA/jdk-8u131-linux-x64.rpm'
                echo 'sudo rpm -ev jdk-8u131-linux-x64.rpm'
                echo 'sudo rpm -Uvh jdk-8u131-linux-x64.rpm'
                echo 'sudo mkdir /opt/java'
                sh 'sudo tar -xvf jdk-8u131-linux-x64.tar.gz -C /opt/java'
                sh 'export JAVA_HOME=/opt/java/jdk1.8.0_131/bin'
                sh 'export JRE_HOME=/opt/java/jdk1.8.0_131/jre'
                sh 'export PATH=$PATH:/opt/java/jdk1.8.0_131/bin:/opt/java/jdk1.8.0_131/jre/bin'
                echo 'sudo mkdir /opt/groovy'
                echo 'sudo cd /home/vinaymachamraj/Downloads'
                echo 'wget http://dl.bintray.com/groovy/maven/apache-groovy-binary-2.4.11.zip'
                sh 'sudo unzip -d /opt/groovy -o apache-groovy-binary-2.4.11.zip'
                sh 'sudo ls /opt/groovy/groovy-2.4.11/bin'
                sh 'export PATH=$PATH:/opt/groovy/groovy-2.4.11/bin'
                sh '/opt/java/jdk1.8.0_131/bin/java -version'
                sh 'puppet --version'
                sh '/opt/groovy/groovy-2.4.11/bin/groovy -version'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                echo 'sudo mkdir /opt/gradle'
                echo 'sudo cd /home/vinaymachamraj/Downloads'
                echo 'sudo wget https://services.gradle.org/distributions/gradle-4.0-bin.zip'
                sh 'sudo unzip -d /opt/gradle -o gradle-4.0-bin.zip'
                sh 'sudo ls /opt/gradle/gradle-4.0/bin'
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
                echo 'export MAVEN_HOME=/opt/maven/apache-maven-3.5.0'
                echo 'export M2_HOME=$MAVEN_HOME/bin'
                sh 'export PATH=$PATH:/opt/maven/apache-maven-3.5.0/bin'
                echo 'sudo wget http://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo'
                echo 'sudo yum check'
                echo 'sudo yum install -y apache-maven'
                sh '/opt/maven/apache-maven-3.5.0/bin/mvn -v'
                echo 'mvn -v'
            }
        }
    }
}
