pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Building project using maven"
                 sh "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }
        stage('copy war file')
        {
            steps{
                sh "scp /var/lib/jenkins/hello-world/workspace/helloworld-1.1.jar vagrant@192.168.33.12/home/vagrant/"
            }
        }
      }
    }
