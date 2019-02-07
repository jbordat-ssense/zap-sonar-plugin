pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                echo "test"
            }
        }
    }
    post {
        always {
            echo "do something"
        }
        failure {
            echo "Failure"
        }
    }
}
