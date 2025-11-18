pipeline {
    agent{
        docker {
            image 'cypress/included:latest'
            args '--entrypoint='
        }
    }
    stages{
        stage('install cypress'){
            sh 'npm ci'
        }
        stage('run tests'){
            sh 'npx cypress run --spec="cypress/e2e/login.cy.js"'
        }
        stage('get junit report'){
            junit 'results/*.xml'
        }
    }
}