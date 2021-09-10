pipeline {
    agent any
    environment { 
        BRANCH_NAME = 'main'
        credentials = 'Jenkins-Test'
    }
    stages {
        stage ('Release Branch') {
            steps {
                git(url: 'https://github.com/osamazia-cloud/CronTestingOsama.git',credentialsId: "${env.credentials}")
                script {
                    sh """
                        date_now=\$(date +%Y-%m-%d)
                        git checkout -b ${env.BRANCH_NAME}-${BUILD_NUMBER}-\$date_now
                        git push --set-upstream origin ${env.BRANCH_NAME}-${BUILD_NUMBER}-\$date_now
                    """
                }
            }
       } 
    } 
}


//git checkout -b ${env.BRANCH_NAME}-\$date_now
//git push --set-upstream origin ${env.BRANCH_NAME}-\$date_now
//date_now=$(date +%Y-%m-%d)