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
                //sh "mvn clean:clean"
                //sh "mvn dependency:copy-dependencies"
                //sh "mvn compiler:compile"
                sh "mvn -X clean compile"
            }
        }
        stage('Exec') {
            steps {
                sh "mvn exec:java"
            }
        }
    }

    post {
        success {
            archiveArtifacts allowEmptyArchive: true,
            artifacts: '*java_proj*.jar'
        }
    }

}