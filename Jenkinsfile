pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Building project using maven"
                 sh "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }
     stage('deploy')
        {
            echo "deploying jar file to tomcat"
            script{
                scp /var/lib/jenkins/hello-world/workspace/target/helloworld-1.1.jar vagrant@192.168.33.10/home/vagrant/apache-tomcat-9.0.37/webapps/
                }
        }
      }
    }
