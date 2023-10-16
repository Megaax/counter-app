pipeline {
    agent any
    tools {
        maven 'Maven 3.9.5'
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
    }
    // Post-build actions or other pipeline configuration can be added here
}
