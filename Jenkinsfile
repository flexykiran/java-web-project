pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                deploy adapters: [tomcat7(credentialsId: 'fc5f7f4f-a0af-4607-a2e6-f1c3d4847695', path: '', 
                url: 'http://ec2-3-124-5-106.eu-central-1.compute.amazonaws.com:8080/')], contextPath: 'javawebapp', 
                war: '**/java-web-project.war'
            }
        }
    }
}
