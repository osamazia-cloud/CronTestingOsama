pipeline {
    agent any
    environment { 
        BRANCH_NAME = 'main'
        credentials = 'test-jenkins'
    }
    stages {
        stage ('Release Branch') {
            steps {
                git url: "ssh://jenkins@your-git-repo:12345/your-git-project.git",
                credentialsId: 'Secret_Key',
                sh 'date_now=\$(date +%Y-%m-%d)'
                branch: "${env.BRANCH_NAME}-\$date_now"
                sh 'git tag -a tagName -m "Your tag comment"'
                sh 'git commit -am "Merged develop branch to master'
                sh "git push origin ${env.BRANCH_NAME}"
                
                
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



// sh """
//                     date_now=\$(date +%Y-%m-%d)
//                     git checkout -b ${env.BRANCH_NAME}-\$date_now
//                     git remote rm origin
//                     git remote add origin 'git@github.com:osamazia-cloud/CronTestingOsama.git'
//                     git checkout -b ${env.BRANCH_NAME}-${BUILD_NUMBER}-\$date_now
//                     git push -u origin ${env.BRANCH_NAME}-${BUILD_NUMBER}-\$date_now
//                 """