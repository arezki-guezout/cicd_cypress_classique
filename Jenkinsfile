pipeline {
    agent {
        docker {
            image 'cypress/included:latest'
            args '-user=root --entrypoint='
        }
    }
    stages{
        stage('install cypress'){
            steps{
                sh 'npm ci'
            }
        }
        stage('run tests'){
            steps{
                sh 'npx cypress run --spec="cypress/e2e/login.cy.js"'
            }
        }
        stage('get junit report'){
            steps{
                junit 'results/*.xml'
            }
        }
    }
}