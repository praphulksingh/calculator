pipeline {
    agent any

    stages {

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

        stage('Deploy') {
            steps {
                sh 'mvn install'
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
            echo '✅ Maven pipeline executed successfully'
        }
        failure {
            echo '❌ Maven pipeline failed'
        }
    }
}
