pipeline {
    agent any
    environment { 
        BRANCH_NAME = 'main'
    }
    stages {
        stage ('Release Branch') {
            steps {
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