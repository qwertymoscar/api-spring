pipeline {
    agent any
    tools {
        maven 'maven363'
    }
    stages {
        stage('Version') {
            steps {
                echo "Testing..."
                sh 'mvn --version'
            }
        }
        stage('clean') {
            steps {
                sh "chmod +x mvnw"
                sh "./mvnw clean"
            }
        }
        stage('Unit Test') {
            steps {
                sh './mvnw test'
            }
        }

        stage('Package') {
            steps {
                sh './mvnw package'
            }
        }
    }
}
