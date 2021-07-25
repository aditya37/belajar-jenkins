pipeline {
    environment {
        SERVICE = 'learn'
    }
    options {
        buildDiscarder(logRotator(daysToKeepStr: env.BRANCH_NAME == 'master' ? '90' : '30'))
    }
}
// Stages jenkins
stages {
    // for git clone
    stage {
        // Validate branch
        when {
            anyOf { branch 'master'; branch 'develop'; branch 'staging' }
        }
        // do clone
        steps {
            echo 'Checking out from Git'
            checkout scm
        }
    }
}

// Stage for build and deploy
stage('Build and deploy') {
    // env
    environment {
        GOPATH = "${env.JENKINS_HOME}/workspace/${env.BRANCH_NAME}"
        PATH = "${env.GOPATH}/bin:${env.PATH}"
    }
    stages {
        stage('Deploy to dev') {
            when {
                branch 'develop'
            }
            environment {
                NAMESPACE = "development"
                SERVICE  = "learn"
            }
            // Do build and deploy
            steps {
                // Do Build
                // sh 'chmod +x build.sh'
                // sh './build.sh default'
                // Do Deploy
            }
        }
    }
}