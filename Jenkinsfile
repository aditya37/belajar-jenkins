pipeline {
    agent {
        node {
            label 'master'
            customWorkspace "workspace/${env.BRANCH_NAME}/src/github.com/aditya37/belajar-jenkins"   
        }
    }
    tools {
        go 'go-1.11'
    }
    environment {
        SERVICE = 'learn-jenkis'
        GO111MODULE = 'on'
    }
    //Parent stages
    stages {
        stage('Checkout') {
            when {
                anyOf { branch 'main'; branch 'develop'; branch 'staging' }
            }
            steps {
                // Ensure the desired Go version is installed
                sh 'go test ./...'
            }
        }
    }
}
