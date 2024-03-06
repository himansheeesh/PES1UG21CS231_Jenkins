pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                sh 'echo "--> building"'
                build 'PES1UG21CS231-1'
                sh 'g++ main.cpp -o output'
            }
        }
        stage('Test') { 
            steps {
                h 'echo "--> in testing"'
                sh './output'

            }
        }
        stage('Deploy') { 
            steps {
                sh 'echo "--> under deployment"' 
                sh 'echo "--> deployed"'
            }
        }
    }
    post{
        failure{
            error '--> pipeline has failed'
        }
    }
}
