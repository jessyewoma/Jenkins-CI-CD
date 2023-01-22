pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // Use appropriate build tool (e.g. Maven or Gradle) to build the project
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                // Use appropriate test tool (e.g. JUnit or TestNG) to run tests
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                // Use the Jenkins Tomcat plugin to deploy the built war file to Tomcat
                sh '''
                export CATALINA_HOME=/path/to/tomcat
                $CATALINA_HOME/bin/catalina.sh stop
                rm -rf $CATALINA_HOME/webapps/calculator
                rm -rf $CATALINA_HOME/webapps/calculator.war
                cp target/calculator.war $CATALINA_HOME/webapps/
                $CATALINA_HOME/bin/catalina.sh start
                '''
            }
        }
    }
}




