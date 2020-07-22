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
                withCredentials([file(credentialsId: 'vagrant2')])
                         {
                      sh "sshpass -p 'vagrant' scp /var/lib/jenkins/workspace/hello-world/target/helloworld-1.1.jar vagrant@192.168.33.12:/home/vagrant/"
                         }
            }
        }
      }
    }
