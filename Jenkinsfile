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
            }
        }
        stage("Test"){
            steps {
                echo "Test UP"
            }
        }
    }
}
