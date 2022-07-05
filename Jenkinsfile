pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                withCredentials([usernamePassword(credentialsId: "testing-cred", usernameVariable: 'USER', passwordVariable: 'PASSWORD')]){
                    docker.withRegistry("https://registry.hub.docker.com/v2/"){
                        def image = docker.image("ubuntu")
                        image.pull()
                        image.inside("") {
                            sh "echo I am here"
                        }
                    }
                    sh 'echo $USER $PASSWORD'
                    sh 'echo Building After Creds..'
                    sh 'chmod 711 cmpstring.sh'
                    sh './cmpstring.sh $PASSWORD password-test'
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
