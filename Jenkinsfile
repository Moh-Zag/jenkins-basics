pipeline {
    agent any

    stages {


        stage('Setup') {
            steps {
                // withCredentials([usernamePassword(credentialsId: 'server-creds', usernameVariable: "myuser", passwordVariable: "mypassword")]) {
                    echo "Setup Stage ..."
                    // sh '''
                    // echo ${myuser}
                    // echo ${mypassword}

                    // pip install -r requirements.txt
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