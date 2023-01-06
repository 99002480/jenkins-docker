pipeline {
    agent{}
    stages {
        stage('Build'){
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
