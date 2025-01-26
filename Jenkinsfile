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
    }
}
