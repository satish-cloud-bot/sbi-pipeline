pipeline{
    agent any
    tools{
        jdk 'myjava'
        maven 'mymaven'
    }
    stages{
        stage('checkout'){
            steps{
            checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/kliakos/sparkjava-war-example.git']])
        }
        }
        stage('create artifact by using mvn'){
            steps{
               sh 'mvn package' 
            }
        }
        stage('deploy'){
            steps{
                sh 'cp -r /var/lib/jenkins/workspace/build-pipeline/target/sparkjava-hello-world-1.0.war /opt/softwares/apache-tomcat-9.0.115/webapps/'
            }
        }
    }
    
    
}
