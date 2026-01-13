pipeline {
    agent any

    stages {

        stage('Validate') {
            steps {
                bat 'mvn validate'
            }
        }

        stage('Compile') {
            steps {
                bat 'mvn compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn package'
            }
        }

        stage('Verify') {
            steps {
                bat 'mvn verify'
            }
        }

        stage('Deploy') {
            steps {
                bat 'mvn install'
            }
        }

        stage('Clean') {
            steps {
                bat 'mvn clean'
            }
        }

        stage('Site') {
            steps {
                bat 'mvn site'
            }
        }
    }

    post {
        success {
            echo '✅ Maven pipeline executed successfully'
        }
        failure {
            echo '❌ Maven pipeline failed'
        }
    }
}
