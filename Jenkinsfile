pipeline {
    agent any
    environment {
        MAVEN_OPTS = "-Dmaven.test.failure.ignore=false"
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/likhith-gowda-014/maven-example.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
                success {
                    echo 'Build and tests succeeded!'
                }
                failure {
                    echo 'Build or tests failed.'
                }
            }
        }
    }
}
