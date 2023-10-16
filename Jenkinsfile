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
        stage('Integration Tests') {
            steps {
                // Maven integration test step
                script {
                    sh 'mvn integration-test'
                }
            }
        }
        stage('Maven Build') {
            steps {
                // Maven integration test step
                script {
                    sh 'mvn clean install'
                }
            }
        }
        // stage('Static Code analysis') {
        //     steps {
        //         // Maven integration test step
        //         script {
        //             withSonarQubeEnv(credentialsId: 'sonar-token'){
        //                 sh'mvn clean package sonar:sonar'
        //             }
        //         }
        //     }
        // }
    }
    // Post-build actions or other pipeline configuration can be added here
}
