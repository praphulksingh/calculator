pipeline {
    agent any

    tools {
        maven 'Maven-3.9'
    }

    environment {
        MAVEN_OPTS = '-Dmaven.repo.local=.m2/repository'
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Building branch: ${env.BRANCH_NAME}"
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            echo "✅ BUILD SUCCESS on branch: ${env.BRANCH_NAME}"
        }
        failure {
            echo "❌ BUILD FAILED on branch: ${env.BRANCH_NAME}"
        }
    }
}
