def getGitBranchName() {
    return scm.branches[0].name
}

pipeline {
    agent any
    environment{
        BRANCH_NAME = "${GIT_BRANCH.split('/').size() == 1 ? GIT_BRANCH.split('/')[-1] : GIT_BRANCH.split('/')[1..-1].join('/')}"
    }
    stages {
        stage('Test') {
            steps {
                script {
                    echo "Testing the application..."
                    echo "Executing pipeline for branch ${BRANCH_NAME}" 
                }
            }
        }

        stage('Build') {
            when {
                expression { env.BRANCH_NAME == 'Doppy6-jenkins-job-fix' } 
            }
            steps {
                script {
                    echo "Building the application..."
                }
            }
        }

        stage('Deploy') {
            when {
                expression { env.BRANCH_NAME == 'Doppy6-jenkins-job-fix' }
            }
            steps {
                script {
                    echo "Deploying the application..."
                }
            }
        }
    }
}
