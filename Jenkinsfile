pipeline {
    agent any

    stages {
        stage('git checkout') {
            steps {
                echo 'get code'
            }
        }

        stage('Test') {
            steps {
                echo 'test'
            }
        }

        stage('build') {
            steps {
                echo 'build'
            }
        }
        
        stage('deploy') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'main') {
                        echo 'dev'
                    } else if (env.BRANCH_NAME == 'uat') {
                        echo 'uat'
                    } else if (env.BRANCH_NAME == 'prod') {
                        echo 'prod'
                    } else {
                        echo "Skipping deployment for branch ${env.BRANCH_NAME}"
                    }
                }
            }
        }
    }
}