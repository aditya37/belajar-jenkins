pipeline {
    environment {
        SERVICE = 'learn'
    }
    options {
        buildDiscarder(logRotator(daysToKeepStr: env.BRANCH_NAME == 'master' ? '90' : '30'))
    }
    stages {
        stage {
            when {
                anyOf { branch 'master'; branch 'develop'; branch 'staging' }
            }
        }
        // Do cLone
        steps {
            echo "Checking out from git"
            checkout scm
        }
    }
}
