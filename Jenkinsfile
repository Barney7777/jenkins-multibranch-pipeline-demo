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
                    if (env.BRANCH_NAME.startsWith('dev/')) {
                        echo 'dev'
                    }
                    else if (env.BRANCH_NAME == 'uat') {
                        echo 'uat'
                    }
                    else if (env.BRANCH_NAME == 'prod') {
                        echo 'prod'
                    }
                    else if (env.CHANGE_TARGET ==~ /refs\/pull\/.*\/merge/) {
                        echo 'Pull request branch'
                        // Additional actions for pull request branches
                    }
                    else {
                        echo "Skipping deployment for branch ${env.BRANCH_NAME}"
                        currentBuild.result = 'UNSTABLE'
                    }
                }
            }
        }
    }
}

