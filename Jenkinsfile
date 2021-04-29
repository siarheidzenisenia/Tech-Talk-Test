
pipeline {
    agent any
    triggers {
        cron('H/15 * * * *')
    }
    options { 
        buildDiscarder(logRotator(daysToKeepStr: '10', numToKeepStr: '100')) 
    }    
    stages {
        stage('Run Tests') {
            steps {
                bat 'newman run Tech_Talk_Test.postman_collection.json --disable-unicode --suppress-exit-code 1'
                } 
            }
        }
    }

