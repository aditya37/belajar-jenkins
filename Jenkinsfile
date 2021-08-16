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
                // Ensure the desired Go version is installed
    def root = tool type: 'go', name: 'Go 1.15'

    // Export environment variables pointing to the directory where Go was installed
    withEnv(["GOROOT=${root}", "PATH+GO=${root}/bin"]) {
        sh 'go version'
    }
            }
        }
    }
}
