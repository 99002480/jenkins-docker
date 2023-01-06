pipeline {
    agent none
    stages {
        stage('Build'){
            agent any
            steps{
                sh 'gcc main.c -fprofile-arcs -ftest-coverage -o output'
                sh './output'
            }
        }
        stage('Test') {
            agent {
                    dockerfile true
                    }
            steps {
                sh 'gcovr'
            }
        }
    }
}
