pipeline {
    agent any

    stages {

        stage('Run Docker Container') {
            steps {
                script {
                    echo 'Запуск нового контейнера...'
                    sh 'docker compose build'
                }
            }
        }
    }

    post {
        success {
            echo 'Процесс завершен успешно!'
        }
        failure {
            echo 'Произошла ошибка в процессе сборки или развертывания.'
        }
    }
}
