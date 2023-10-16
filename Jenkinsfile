pipeline {
    agent any
    tools {
        maven 'myMaven'
    }
    stages {
        stage('Git Checkout') {
            steps {
                // Checkout the code from the Git repository
                git branch: 'main', url: 'https://github.com/Megaax/counter-app'
            }
        }
        stage('Unit Test') {
            steps {
               script {
                    // Run Maven unit tests
                    sh 'mvn test'
                }
            }
        }
        stage('Run Integration Tests') {
            steps {
                // Maven integration test step
                script {
                    sh 'mvn  -DskipUnitTests'
                }
            }
        }
    }
    // Post-build actions or other pipeline configuration can be added here
}
