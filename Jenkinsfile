pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                git 'https://github.com/pranit321/web-app.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://16.171.41.131:8080')], contextPath: null, war: 'targets/*.war'
            }
        }
    }
}
