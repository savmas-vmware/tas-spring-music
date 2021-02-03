pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                echo 'Start Build...'
                sh './gradlew clean build'
            }
        }
        stage('Test') { 
            steps {
                echo 'Run Tests...'
                sh './gradlew clean test'
            }
        }
        stage('Assemble') { 
            steps {
                echo 'Assemble Project...'
                sh './gradlew clean assemble'
            }
        }
        stage('Deploy') { 
            steps {
                echo 'Deploy to TAS'
                sh 'cf login -a https://api.sys.paris.cf-app.com -u admin -p b-pw_UsF3yhvFWr3P7wlE93zp5k3Z6BJ --skip-ssl-validation -o org-2 -s org-2-dev'
                sh 'cf push spring-music'
                echo 'Deployment Complete!'
            }
        }
    }
}
