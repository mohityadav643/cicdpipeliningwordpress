pipeline {
    stages {
        stage("checkout") {
            steps {
                git url: 'https://github.com/mohityadav643/cicdpipeliningwordpress.git', branch: 'master'
            }
        }
        stage("build and deploy") {
            steps {
                sh '''
                docker compose down || true
                docker compose up -d --build
                '''
            }
        }
    }
    post {
        success {
            script {
                echo "Build completed successfully."
            }
        }
        failure {
            script {
                echo "Build failed."
            }
        }
    }
}