pipeline {
    agent any
    options {
        ansiColor('xterm')
        timestamps()
    }
    stages {
        stage('Git') {
            steps {
                git poll: false, url: 'https://github.com/mrogacew/spring-demo.git'
            }
        }
        stage('Build') {
            steps {
                bat label: '', script: 'mvn clean package'
            }
        }
        stage('Report') {
            steps {
                junit '**/target/surefire-reports/*.xml'
            }
        }
    }
}