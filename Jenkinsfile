// pipeline {
//     agent any

//     stages {
//         stage('Checkout SCM') {
//             steps {
//                 git credentialsId: 'git-ssh-credentials',
//                       url: 'https://github.com/thayeeb-9211/DevOps.git',
//                       branch: 'new-feature'
//             }
//         }
//         stage('Build') {
//             steps {
//                 sh 'make build' // or your build command
//             }
//         }
//         stage('Commit and Push') {
//             steps {
//                 sh 'git config --global user.email "devgenius9211@gmail.com"'
//                 sh 'git config --global user.name "thayeeb-9211"'
//                 sh 'git add .'
//                 sh 'git commit -m "Automated commit from Jenkins"'
//                 sh 'git push origin new-feature'
//             }
//         }
//     }
// }




// pipeline {
//     agent any
//     stages {
//         stage('jenkins first step') {
//             steps {
//                 echo 'welcome thayeeb'
//             }
//         }
//     }
// }



// pipeline {
//     agent any

//     environment {
//         // Your GitHub credentials stored in Jenkins (Create them in Jenkins -> Manage Credentials)
//         GITHUB_CREDENTIALS = credentials('github-credentials-id') 
//     }

//     stages {
//         stage('Checkout Code') {
//             steps {
//                 // Check out code from GitHub
//                 git branch: 'main', url: 'https://github.com/thayeeb-9211/DevOps.git'
//             }
//         }
        
//         stage('Make Changes') {
//             steps {
//                 // Shell script to modify files, if required
//                 sh '''
//                 echo "Making some changes to files..."
//                 # Example command: echo "New content" >> somefile.txt
//                 '''
//             }
//         }

//         stage('Commit Changes') {
//             steps {
//                 // Commit the changes
//                 sh '''
     
//                 git add .
//                 git commit -m "Automated commit from Jenkins"
//                 '''
//             }
//         }
//                 // git config --global user.email "your-email@example.com"
//                 // git config --global user.name "your-username"

//         stage('Push Changes to GitHub') {
//             steps {
//                 // Push the changes back to GitHub using the credentials
//                 sh '''
//                 git push https://$GITHUB_CREDENTIALS_USR:$GITHUB_CREDENTIALS_PSW@github.com/your-username/your-repo.git
//                 '''
//             }
//         }
//     }
    
//     post {
//         always {
//             echo 'Pipeline finished'
//         }
//     }
// }




pipeline {
    agent any

    environment {
        // Your GitHub credentials stored in Jenkins (Create them in Jenkins -> Manage Credentials)
        GITHUB_CREDENTIALS = credentials('github-credentials-id') 
        TARGET_BRANCH = 'new-feature'  // Specify your target branch here
    }

    stages {
        stage('Checkout Code') {
            steps {
                // Check out code from the specific branch on GitHub
                git branch: "${TARGET_BRANCH}", url: 'https://github.com/thayeeb-9211/DevOps.git'
            }
        }

        stage('Make Changes') {
            steps {
                // Shell script to modify files, if required
                sh '''
                echo "Making some changes to files..."
                # Example command: echo "New content" >> somefile.txt
                '''
            }
        }

        stage('Commit Changes') {
            steps {
                // Commit the changes
                sh '''
                git add .
                git commit -m "Automated commit from Jenkins"
                '''
            }
        }

        stage('Push Changes to GitHub') {
            steps {
                // Push the changes back to the specific branch using the credentials
                sh '''
                git push https://$GITHUB_CREDENTIALS_USR:$GITHUB_CREDENTIALS_PSW@github.com/thayeeb-9211/DevOps.git ${TARGET_BRANCH}
                '''
            }
        }
    }
    
    post {
        always {
            echo 'Pipeline finished'
        }
    }
}
