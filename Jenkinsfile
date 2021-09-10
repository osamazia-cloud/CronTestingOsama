pipeline {
    agent any
    environment { 
        BRANCH_NAME = 'main'
        credentials = 'test-jenkins'
    }
    stages {
        stage ('Release Branch') {
            steps {
                withCredentials([string(credentialsId: 'Secret_Key', variable: 'TOKEN')]) {
                    sh """
                        date_now=\$(date +%Y-%m-%d)
                        git checkout -b ${env.BRANCH_NAME}-${BUILD_NUMBER}-\$date_now
                        git remote rm origin
                        git remote add origin git@github.com:osamazia-cloud/CronTestingOsama.git
                        ssh-keygen -R domain.com
                        ssh-keyscan -t rsa domain.com >> ~/.ssh/known_hosts
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


// script {
//                     sh """
//                         date_now=\$(date +%Y-%m-%d)
//                         git checkout -b ${env.BRANCH_NAME}-${BUILD_NUMBER}-\$date_now
//                         git push --set-upstream origin ${env.BRANCH_NAME}-${BUILD_NUMBER}-\$date_now
//                     """
//                 }