pipeline {
    agent any
    
    tools {
      
        maven 'local_maven' 
        jdk 'java25'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/ixsnehith/hello-world-war.git'
            }
        }

        stage('Build') {
            steps {
               
                sh 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
               
                deploy adapters: [tomcat9(credentialsId: 'tomcat-creds', path: '', url: 'http://3.110.156.189:9090')], 
                       contextPath: 'myapp',
                       war: 'target/*.war'
            }
        }
    }
}
