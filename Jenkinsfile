
pipeline {
    agent any
    triggers {
        cron('H/15 * * * *')
    }
    options { 
        buildDiscarder(logRotator(daysToKeepStr: '10', numToKeepStr: '100')) 
    }    
    }
    stages {
        stage('Run Tests') {
            steps {
                        sh 'newman run *.postman_collection.json'
                } 
            }
        }
    }
