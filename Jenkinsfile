@Library('jenkinsLib@feat/DEVOPS-1079_auto_apps_security_scans') _

pipeline {
    agent any
    stages {

        def config = [
          debug: true,
          mvn_command_line: "clean package -DskpiTests",
        ]

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
