pipeline {
    agent any

    tools {
        maven 'maven'
    }

    stages {
        stage('Code') {
            steps {
                git 'https://github.com/harish000111/one.git'
            }
        }

        stage('Build and Test') {
            parallel {
                stage('Build') {
                    steps {
                        sh 'mvn package -DskipTests'
                    }
                }

                stage('Test') {
                    steps {
                        sh 'mvn test'
                    }
                }
            }
        }
    }
}
