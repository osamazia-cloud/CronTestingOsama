pipeline {
    agent any
    environment { 
        BRANCH_NAME = 'main'
        credentials = 'test-jenkins'
    }
    stages {
        stage ('Release Branch') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'git-cre',usernameVariable: 'username', passwordVariable: 'password')]){
                    sh """
                    date_now=\$(date +%d-%m-%Y)
                    git remote set-url origin https://\$username:\$password@github.com/osamazia-cloud/CronTestingOsama.git
                    git checkout -b ${env.BRANCH_NAME}-${BUILD_NUMBER}-\$date_now
                    git push --set-upstream origin ${env.BRANCH_NAME}-${BUILD_NUMBER}-\$date_now
                    """
                }
            }
       }
    } 
}
