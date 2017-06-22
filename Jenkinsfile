pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'java --version'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'gradle --version'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh 'mvn --version'
            }
        }
    }
}
