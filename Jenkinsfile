pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello from Github polling trigger'
            }
        }
        stage('Build') {
            steps {
                echo 'Building'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying'
                script {
                    // Nginxコンテナ名（Docker Composeなどで定義されている名前）
                    def nginxContainer = 'nginx-test'

                    // JenkinsコンテナからNginxコンテナへファイルをコピー
                    sh """
                        docker cp ./src/. ${nginxContainer}:/usr/share/nginx/html/
                    """
                }

            }
        }
        stage('Test') {
            steps {
                echo 'Testing'
            }
        }
        stage('Release') {
            steps {
                echo 'Releasing'
            }
        }
    }
}
