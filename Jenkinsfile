pipeline {
    agent {
        label 'slave-00'
        customWorkspace "workspace/${env.BRANCH_NAME}/src/github.com/aditya37/belajar-jenkins"
    }
    environment {

    }
    stages {
        stage('Checkout') {
            when {
                anyOf { branch 'main'; branch 'develop'; branch 'staging' }
            }
            steps {
                echo 'Checking out from Git'
                checkout scm
            }
        }
    }
}