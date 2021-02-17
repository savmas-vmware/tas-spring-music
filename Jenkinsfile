pipeline {
    agent any 
    stages {
        stage('Assemble Project') { 
            steps {
                echo 'Assemble Project...'
                sh './gradlew clean assemble'
            }
        }
        stage('Deploy to TAS') { 
            steps {
                echo 'Deploy to TAS...'
                sh 'cf login -a https://api.sys.tas.platformdemosm.com -u admin -p tas_admin --skip-ssl-validation -o demo-org -s dev'
                sh 'cf push spring-music'
                echo 'Deployment Completed!'
            }
        }
    }
}
