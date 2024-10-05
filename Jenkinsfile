pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Клонируем репозиторий с GitHub
                git 'https://github.com/MounTemed/test_pipeline.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                // Собираем Docker-образ
                script {
                    docker.build('my-python-app')
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                // Запускаем контейнер
                script {
                    docker.image('my-python-app').run('-p 5000:5000')
                }
            }
        }
    }
}

