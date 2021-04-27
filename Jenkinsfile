@Library(['piper-lib', 'piper-lib-os']) _

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
                dockerExecute(script: this, dockerImage: 'postman/newman'){
                    withCredentials([file(credentialsId: "${params.CPI_ENVIRONMENT_ID}", variable: 'CPI_ENVIRONMENT')]) {
					
                        sh 'newman run *.postman_collection.json'
                    }  
                } 
            }
        }
    }
}
