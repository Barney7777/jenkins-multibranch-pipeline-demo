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
                        echo 'main'
                    }
                    else if (env.BRANCH_NAME.startsWith('dev/')) {
                        echo 'dev'
                    }
                    else if (env.BRANCH_NAME == 'uat') {
                        echo 'uat'
                    }
                    else if (env.BRANCH_NAME == 'prod') {
                        echo 'prod'
                    }
                    else {
                        error("Skipping deployment for branch ${env.BRANCH_NAME}")
                    }
                }
            }
        }
    }
}
