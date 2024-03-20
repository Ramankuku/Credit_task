pipeline {
    agent any

    environment {
        DIRECTORY_PATH = "https://github.com/Ramankuku/Credit_task"
        TESTING_ENVIRONMENT = "ramans TestingEnv"
        PRODUCTION_ENVIRONMENT = "raman"
    }

    stages {
        stage('Build') {
            steps {
                echo "Fetching the source code from the directory path specified by the environment variable: ${env.DIRECTORY_PATH}"
                echo "Compiling the code and generating any necessary artifacts, updated"
             echo "updatting"
              
            }
        }
        stage('Test') {
            steps {
                echo "Running unit tests"
                echo "Running integration tests"
                echo "update"
            }
            post {
                success {
                    emailext  subject: 'Unit Test Status - Success', 
                              body: 'Unit Test has been completed successfully.', 
                              to: "raman89765038@gmail.com",
                              attachLog: true
                }
                failure {
                    emailext subject: 'Unit Test Status - Failure', 
                              body: 'Unit Test has failed.', 
                              to: "raman89765038@gmail.com",
                              attachLog: true
                }
            }
        }
        stage('Code Quality Check') {
            steps {
                echo "Checking the quality of the code"
            }
        }
        stage('Security Scan') {
            steps {
                echo "Performing security scan on the code"
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Deploying the application to a testing environment specified by the environment variable: ${env.TESTING_ENVIRONMENT}"
            }
            post {
                success {
                    emailext  subject: 'Security Scan Status - Success', 
                              body: 'Security Scan has been completed successfully.', 
                              to: "raman89765038@gmail.com",
                              attachLog: true
                }
                failure {
                    emailext subject: 'Security Scan Status - Failure', 
                              body: 'Security Scan has failed.', 
                              to: "raman89765038@gmail.com",
                              attachLog: true
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests on the staging environment"
                echo "updating the script"
            }
        }
        stage('Approval') {
            steps {
                script {
                    echo "Pausing for manual approval..."
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying the code to the production environment "
               
            }
        }
    }
}
