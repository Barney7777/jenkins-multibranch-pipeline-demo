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
                echo 'uat'
            }
        }
    }
}