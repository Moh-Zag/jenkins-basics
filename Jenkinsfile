pipeline {
    agent any

    stages {


        stage('Setup') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'a123890d-3c24-4c57-9fd5-7b3996683427', usernameVariable: "myuser", passwordVariable: "mypassword")]) {

                    sh '''
                    echo ${myuser}
                    echo ${mypassword}
                    '''
                }
                sh "apt install python3.12-venv"
                sh "python3 -m venv venv"
                sh "venv/pip install -r requirements.txt"
            
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
}