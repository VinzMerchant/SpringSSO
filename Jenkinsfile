pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh '#!/bin/bash'
                echo 'sudo yum install sdkman'
                sh 'java -version'
                sh 'puppet --version'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'mkdir /opt/gradle'
                sh 'cd /home/vinaymachamraj/Downloads'
                sh 'wget https://services.gradle.org/distributions/gradle-4.0-bin.zip'
                sh 'unzip -d /opt/gradle gradle-4.0-bin.zip'
                sh 'ls /opt/gradle/gradle-4.0'
                sh 'export PATH=$PATH:/opt/gradle/gradle-4.0/bin'
                sh 'gradle -version'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh 'mvn -version'
            }
        }
    }
}
