pipeline {
    agent any

    tools {
        maven 'Maven3'
    }

    stages {

        stage('Git Pull') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Arundhuti-Deka/maven-webapp.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
                sh 'cp target/maven-webapp.war /home/ec2-user/tomcat/webapps/'
            }
        }
    }
}
