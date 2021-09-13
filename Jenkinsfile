pipeline {
    agent any
    stages {
        stage ('Release Branch') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'git-cre',usernameVariable: 'username', passwordVariable: 'password')]){
                    sh """
                    date_now=\$(date +%d-%m-%Y)
                    git remote set-url origin https://\$username:\$password@github.com/osamazia-cloud/CronTestingOsama.git
                    git checkout -b releasea/\$date_now
                    git push --set-upstream origin releasea/\$date_now
                    """
                }
            }
       }
    } 
}
