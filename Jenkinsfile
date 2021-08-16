pipeline {
    agent {
        node {
            label 'master'
            customWorkspace "workspace/${env.BRANCH_NAME}/src/github.com/aditya37/belajar-jenkins"   
        }
    }
    tools {
        go 'go1.16.4'
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
            environment {
                PATH = "${env.GOPATH}/bin:${env.PATH}"
            }
            steps {
                // Ensure the desired Go version is installed
                sh './usr/local/go/bin/go test'
            }
        }
    }
}
