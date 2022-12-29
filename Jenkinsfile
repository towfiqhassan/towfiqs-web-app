pipeline {
    agent any
    stages {
        stage("Clean Up"){
            steps {
                echo "Clean UP"
                deleteDir()
            }
        }
        stage("Clone Repo"){
            steps {
                sh "git clone https://github.com/towfiqhassan/towfiqs-web-app.git"
                dir("towfiqs-web-app") {
                sh "date > output.txt"
                }
            }
        }
        stage("Build"){
            steps {
                echo "Build UP"
                script {         
                    def customImage = docker.build('cloudformula/simple-web-app', "./docker")
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
                    customImage.push("${env.BUILD_NUMBER}")
                    }                     
            }
            }
        }
        stage("Test"){
            steps {
                echo "Test UP"
            }
        }
    }
}
