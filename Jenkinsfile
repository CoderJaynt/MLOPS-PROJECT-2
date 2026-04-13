pipeline{
    agent any

    stages{
        stage("Cloning from Github...."){
            script{
                echo 'Cloning from Github...'
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-token', url: 'https://github.com/CoderJaynt/MLOPS-PROJECT-2.git']])
            }
        }
    }
}