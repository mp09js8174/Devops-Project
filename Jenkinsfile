pipeline {
    agent {
       node { 
          label 'maven'
       }
} 
    stages {
        stage('Checkout From SCM') {
            steps {
                checkout scmGit(branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/mp09js8174/Devops-Project.git']])
            }
        }
    }
}
