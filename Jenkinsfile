pipeline {
    agent any

    stages {
        stage('Build') {
            withCredentials([usernamePassword(credentialsId: "testing-cred", usernameVariable: 'USER', passwordVariable: 'PASSWORD')]){
                echo $USER $PASSWORD
            }
            steps {
                echo 'Building..'
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
