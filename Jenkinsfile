pipeline {
    agent any

    stages {
        stage('GetProject') {
            steps {
                git 'https://github.com/MT-byte/java_proj'
            }
        }
        stage('Build') {
            steps {
                sh "mvn clean:clean"
                //sh "mvn dependency:copy-dependencies"
                sh "mvn compiler:compile"
            }
        }
        stage('Exec') {
            steps {
                sh "mvn exec:java"
            }
        }
    }
}