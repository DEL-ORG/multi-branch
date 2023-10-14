pipeline {
    agent any
     triggers {
        githubPush() // This will trigger the build on GitHub push events
    }

    options {
        // Define pipeline options here
        timeout(time: 1, unit: 'HOURS') // Set a time limit for the entire pipeline
        buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '10')) // Configure build and artifact retention
        disableConcurrentBuilds() // Prevent concurrent builds of the same pipeline
    }

    parameters {
        // Define input parameters here
        string(name: 'BRANCH_NAME', defaultValue: 'dev', description: '')
    }

    environment {
        // Define environment variables here
        DB_USERNAME = 'admin'
        DB_PASSWORD = 'admin'
    }

    stages {
        // Define stages and steps here
        stage('Checkout') {
            steps {
                sh """
                  echo "cloning the repo, please wait ........"
                  sleep 5
                """
            }
        }

        stage('Build') {
            steps {
                sh """
                  echo "building the code, please wait ........."
                  sleep 5
                """
            }
        }

        stage('Scan') {
            steps {
                sh """
                  echo "scanning the code, please wait ........"
                  sleep 5
                """
            }
        }

        // Add more stages as needed

        stage('Clean Up') {
            steps {
                sh """
                  echo "clean up, please wait ........"
                  sleep 5
                """
            }
        }
    }

    post {
        success {
            // Actions to perform when the pipeline is successful
            echo 'Pipeline completed successfully!'
        }
        failure {
            // Actions to perform when the pipeline fails
            echo 'Pipeline failed!'
        }
        always {
            // Actions to perform regardless of success or failure
            echo 'Pipeline finished'
        }
    }
}


