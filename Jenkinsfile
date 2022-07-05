pipeline {
    agent any

    stages {
        stage('Build') {
            withCredentials([usernamePassword(credentialsId: "testing-cred", usernameVariable: 'USER', passwordVariable: 'PASSWORD')]){
                steps {
                    echo $USER $PASSWORD
                    echo 'Building After Creds..'
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
