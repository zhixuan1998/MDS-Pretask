pipeline {
    agent any

    environment {
        dockerImage = ''
        DOCKER_IMAGE = "zhixuan/mds-pretask:latest"
    }

    stages {
        stage('Build') {
            steps {
                script {
                    echo "Cloning repository..."
                }
                git branch: 'main', url: 'https://github.com/zhixuan1998/MDS-Pretask.git'
            }
            script {
                    echo "Building Docker image..."
                    dockerImage = docker.build DOCKER_IMAGE
                }
        }
    }

    post {
        always {
            echo 'Pipeline complete.'
        }
    }
}
