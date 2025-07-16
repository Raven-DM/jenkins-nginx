pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('hello-nginx-image')
                }
            }
        }
        stage('Run Container') {
            steps {
                sh 'docker rm -f hello-nginx-container || true'
                sh 'docker run -d --name hello-nginx-container -p 8081:80 hello-nginx-image'
            }
        }
    }
}
