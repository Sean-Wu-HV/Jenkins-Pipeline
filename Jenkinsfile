pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                withCredentials([usernamePassword(credentialsId: "testing-cred", usernameVariable: 'USER', passwordVariable: 'PASSWORD')]){
                    sh 'echo $USER $PASSWORD'
                    sh 'echo Building After Creds..'
                    sh '.cmpstring.sh $PASSWORD password-test'
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
