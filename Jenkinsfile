pipeline {
    agent {
       node { 
          label 'maven'
       }
} 
environment {
    PATH = "/opt/maven/bin:$PATH" 
}
    stages {
        stage('Build') {
            steps {
                echo "----------- build started ----------"
                 sh 'mvn clean deploy -Dmaven.test.skip=true'
                echo "----------- build complted ----------"

            }
        }

          stage('Test') {
            steps {
                echo "----------- Unit Test Started ----------"
                 sh 'mvn surefire-report:report'
                echo "----------- Unit Test complted ----------"

            }
        }
          stage('SonarQube analysis') {
          environment {
           scannerHome = tool 'sonar-scanner'
          }
           steps{
               withSonarQubeEnv('sonarqube-server') { // If you have configured more than one global server connection, you can specify its name
               sh "${scannerHome}/bin/sonar-scanner"
          }
          }
    }
}
