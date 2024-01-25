pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application'
                // Add your build commands here
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests'
                // Add your test commands here
            }
        }

        stage('Deploy to Staging') {
            when {
                expression {
                    return (env.BRANCH_NAME == 'develop' || env.BRANCH_NAME.startsWith('feature/'))
                }
            }
            steps {
                echo 'Deploying to Staging environment'
                // Add your staging deployment commands here
            }
        }

        stage('Deploy to Production') {
            when {
                expression {
                    return (env.BRANCH_NAME == 'master')
                }
            }
            steps {
                echo 'Deploying to Production environment'
                // Add your production deployment commands here
            }
        }
    }

    post {
        success {
            echo 'Pipeline successful. Send notifications or perform additional actions here.'
        }
        failure {
            echo 'Pipeline failed. Send notifications or perform additional actions here.'
        }
    }
}
