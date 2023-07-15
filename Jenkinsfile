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
                if (env.BRANCH_NAME == 'main') {
                    echo 'main'
                }
                else if (env.BRANCH_NAME.startsWith('dev/')) {
                    echo 'dev'
                }
                else if (env.BRANCH_NAME == 'uat') {
                    echo 'uat'
                }
                else if (env.BRANCH_NAME == 'prod1') {
                    echo 'prod'
                }
                else {
                    error("Skipping deployment for branch ${env.BRANCH_NAME}")
                }
            }
        }
    }
}

    // post {
    //     always {
    //         script {
    //             if (env.BRANCH_NAME == 'devops-barney') {
    //                 error('Skipping pipeline for devops-barney branch')
    //             }
    //         }
    //     }
    // }
    // the post section with the always block is added at the end of the pipeline. 
    // It checks if the BRANCH_NAME is equal to 'devops-barney' and throws an error using the error step, which stops the pipeline execution for that branch.
    // Now, when the Jenkins Multibranch Pipeline is executed, 
    // the pipeline will skip the deploy stage and terminate for the devops-barney branch, while continuing for the other branches.

