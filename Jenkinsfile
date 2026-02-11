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
               
                bat 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
              bat 'copy target\\*.war C:\\tomcat\\webapps'

            }
        }
    }
}
