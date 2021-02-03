pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                echo 'Starting Build...'
                sh './gradlew clean assemble'
            }
        }
        stage('Test') { 
            steps {
                echo 'Test Stage started' 
            }
        }
        stage('Deploy') { 
            steps {
                echo 'Deploy Stage started'
            }
        }
    }
}
