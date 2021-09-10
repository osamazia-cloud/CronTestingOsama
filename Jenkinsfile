pipeline {
    agent any
    environment { 
        BRANCH_NAME = 'main'
        credentials = 'test-jenkins'
    }
    stages {
        stage ('Release Branch') {
            steps {
                
                sh """
                    date_now=\$(date +%Y-%m-%d)
                    ssh-keyscan -t rsa github.com >> ~/.ssh/known_hosts
                    eval "$(ssh-agent -s)"
                    ssh-add
                    git checkout -b ${env.BRANCH_NAME}-${BUILD_NUMBER}-\$date_now
                    git push --set-upstream origin ${env.BRANCH_NAME}-${BUILD_NUMBER}-\$date_now
                """
                
            }
       } 
    } 
}

// withCredentials([string(credentialsId: 'Secret_Key', variable: 'TOKEN')]) {
//git checkout -b ${env.BRANCH_NAME}-\$date_now
//git push --set-upstream origin ${env.BRANCH_NAME}-\$date_now
//date_now=$(date +%Y-%m-%d)
// git remote add origin 'git@github.com:osamazia-cloud/CronTestingOsama.git'
// git remote rm origin
// script {
//                     sh """
//                         date_now=\$(date +%Y-%m-%d)
//                         git checkout -b ${env.BRANCH_NAME}-${BUILD_NUMBER}-\$date_now
//                         git push --set-upstream origin ${env.BRANCH_NAME}-${BUILD_NUMBER}-\$date_now
//                     """
//                 }