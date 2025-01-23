pipeline {
    agent {
       node { 
          label 'maven'
       }
} 
    stages {
        stage('Hello') {
            steps {
                checkout scmGit(branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/mp09js8174/Devops-Project.git']])
            }
        }
    }
}
