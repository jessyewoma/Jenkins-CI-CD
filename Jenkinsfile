pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'scp target/*.war http://3.83.100.92/@tomcat:/path/to/webapps'
                sh 'ssh user@tomcat "./bin/shutdown.sh && ./bin/startup.sh"'
            }
        }
    }
}

