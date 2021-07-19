pipeline {
    agent any
    stages{
        stage("Init") {
            steps {
                checkout scm
            }
        }
        stage("Install Dependencies"){
            steps {
                sh 'npm install'
            }
        }
        stage("Run E2E Test"){
            steps {
                sh 'npm run test'
            }
        }
        stage("Build for Production"){
            steps {
                sh 'npm run build'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy to production'
            }
        }
    }
    post{
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}