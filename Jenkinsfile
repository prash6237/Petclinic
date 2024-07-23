pipeline {
    agent any
    
    tools {
        jdk 'jdk11'
        maven 'maven3'
    }
    
    stages {
        
        stage('Git Checkout') {
            steps {
                git branch: 'feature', url: 'https://github.com/jaiswaladi246/Petclinic.git'
            }
        }

    
        stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                sh 'cp target/*.war  /opt/apache-tomcat-9.0.65/webapps'
            }
        }
   
    }
}
