pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building..'
          }
        }

        stage('dev_build') {
          steps {
            bat 'echo "Hello dev build"'
          }
        }

        stage('SIT Build') {
          steps {
            timestamps() {
              echo 'SIT Build'
            }

          }
        }

        stage('UAT BUILD') {
          steps {
            bat 'echo "Build of UAT"'
          }
        }

        stage('Staging Build') {
          steps {
            echo 'Building for staging'
          }
        }

      }
    }

    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            echo 'Testing..'
            echo 'sudo mkdir /opt/gradle'
            echo 'sudo cd /home/vinaymachamraj/Downloads'
            echo 'sudo wget https://services.gradle.org/distributions/gradle-4.0-bin.zip'
            #sh 'sudo unzip -d /opt/gradle -o gradle-4.0-bin.zip'
            #sh 'sudo ls /opt/gradle/gradle-4.0/bin'
            #sh 'export PATH=$PATH:/opt/gradle/gradle-4.0/bin'
            #sh '/opt/gradle/gradle-4.0/bin/gradle -v'
            #sh 'cd ~'
          }
        }

        stage('Dev Test') {
          steps {
            powershell 'write-host "the new value is Dev Test"'
          }
        }

        stage('Test SIT') {
          steps {
            timeout(time: 15, activity: true)
          }
        }

        stage('UAT Test') {
          steps {
            echo 'UAT Test running'
          }
        }

        stage('Staging Test') {
          steps {
            bat 'echo "Testing in Staging"'
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deploying....'
            echo 'sudo mkdir /opt/maven'
            #sh 'sudo cd /home/vinaymachamraj/Downloads'
            echo 'sudo wget http://mirror.olnevhost.net/pub/apache/maven/maven-3/3.5.0/binaries/apache-maven-3.5.0-bin.tar.gz'
            #sh 'sudo tar -xvf apache-maven-3.5.0-bin.tar.gz -C /opt/maven'
            #sh 'sudo ls /opt/maven/apache-maven-3.5.0/bin'
            echo 'export MAVEN_HOME=/opt/maven/apache-maven-3.5.0'
            echo 'export M2_HOME=$MAVEN_HOME/bin'
            #sh 'export PATH=$PATH:/opt/maven/apache-maven-3.5.0/bin'
            echo 'sudo wget http://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo'
            echo 'sudo yum check'
            echo 'sudo yum install -y apache-maven'
            #sh '/opt/maven/apache-maven-3.5.0/bin/mvn -v'
            echo 'mvn -v'
          }
        }

        stage('Deploy in DEV') {
          steps {
            echo 'deployment is in progress'
          }
        }

        stage('Deploy SIT') {
          steps {
            bat 'echo "Deployment in Progress of SIT"'
          }
        }

        stage('UAT Deployment') {
          steps {
            powershell 'write-host "the new value is UAT  Deployment"'
          }
        }

        stage('Staging Deployment') {
          steps {
            echo 'deploying in staging'
          }
        }

      }
    }

  }
}
