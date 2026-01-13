pipeline {
    agent any

    tools {
        jdk 'JDK'
        maven 'Maven'
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/USERNAME/REPO_NAME.git'
            }
        }

        stage('Validate') {
            steps {
                sh 'mvn validate'
            }
        }

        stage('Compile') {
            steps {
                sh 'mvn compile'
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

        stage('Verify') {
            steps {
                sh 'mvn verify'
            }
        }

        stage('Install') {
            steps {
                sh 'mvn install'
            }
        }

        stage('Deploy') {
            steps {
                sh 'mvn deploy'
            }
        }

        stage('Clean') {
            steps {
                sh 'mvn clean'
            }
        }

        stage('Site') {
            steps {
                sh 'mvn site'
            }
        }
    }

    post {
        success {
            echo '✅ GitHub Maven project built with all 9 goals'
        }
        failure {
            echo '❌ Pipeline failed'
        }
    }
}
