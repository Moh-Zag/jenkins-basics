pipeline {
            agent any

    stages {
            agent { docker { image 'python:3.12.0b3-alpine3.18'
    
                label 'docker-on-vas'
            }
            }

        stage('Setup') {
            steps {
                // withCredentials([usernamePassword(credentialsId: 'server-creds', usernameVariable: "myuser", passwordVariable: "mypassword")]) {
                    echo "Setup Stage ..."
                    sh '''
                    // echo ${myuser}
                    // echo ${mypassword}

                    pip install -r requirements.txt
                    // '''
                }
            }
        
        stage('Test') {
            steps {
                sh "pytest"
                
            }
        }    
        stage('Deployment') {
            input {
                message "Do you want to proceed further?"
                ok "Yes"
            }
            steps {
                echo "Running Deployment"
                
            }
        } 
        
            
    }
    
    // post {
    //     always{
    //         cleanWs()
    //     }
    // }
    
}