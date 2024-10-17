pipeline {
    agent any
    
    tools{
        jdk 'jdk17'
        nodejs 'node16'
        
    }
    
    
    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/ifty786/fullstack-bank.git'
            }
        }
        
       
         stage('Install Dependencies') {
            steps {
                dir('app/backend') {
                    sh 'npm install'
                }
                dir('app/frontend') {
                    sh 'npm install'
                }
            }
        }
        
         stage('Deploy to Conatiner') {
            steps {
                sh "npm run compose:up -d"
            }
        }
    }
}
