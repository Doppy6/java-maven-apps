pipeline {
    agent any

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
