pipeline {
    agent any
    stages {
        stage ('Release Branch') {
            steps {
                sh "!/bin/bash"
                sh "date_now=$(date +%Y-%m-%d)"
                sh "git checkout -b ${env.BRANCH_NAME}-\$date_now"
                sh "git push --set-upstream origin ${env.BRANCH_NAME}-\$date_now"
               
            }
       } 
    } 
}
