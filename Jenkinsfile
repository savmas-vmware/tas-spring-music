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
                sh 'cf login -a https://api.sys.paris.cf-app.com -u admin -p b-pw_UsF3yhvFWr3P7wlE93zp5k3Z6BJ --skip-ssl-validation -o org-2 -s org-2-dev'
                sh 'cf push spring-music'
            }
        }
    }
}
