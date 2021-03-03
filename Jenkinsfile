pipeline {
    agent any
    tools {
        maven 'maven363'
    }
    stages {
        stage('Parallel version') {
            parallel {
                stage('Version') {
                    steps {
                        echo "Testing..."
                        sh 'mvn --version'
                    }
                }
                stage('Package') {
                    steps {
                        sh 'mvn package -DskipTest'
                    }
                }
            }
        }
        stage('Unit Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
