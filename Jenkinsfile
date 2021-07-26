pipeline {
    agent {
        node {
            label 'master'
            customWorkspace "workspace/${env.BRANCH_NAME}/src/github.com/aditya37/belajar-jenkins"   
        }        
    }
    environment {
        SERVICE = 'learn-jenkis'
    }
    //Parent stages
    stages {
        stage('Checkout') {
            when {
                anyOf { branch 'main'; branch 'develop'; branch 'staging' }
            }
            steps {
                echo 'Checking out from Git'
                checkout scm
                sh 'docker-compose'
            }
        }
    }
}
