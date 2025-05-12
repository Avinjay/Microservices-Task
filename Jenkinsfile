pipeline {
    agent any
    environment {
        GITURL = "https://github.com/Avinjay/Microservices-Task.git"
    }
    stages {
        
        stage('Git Clone') {
            steps {
                git branch: 'main', url: "${env.GITURL}"
            }
        }
        
        stage('Build and Lint Services') {
            parallel {
                stage('Build user-service') {
                    steps {
                        dir('./Microservices/user-service') {
                            sh 'npx eslint . || true'
                            sh 'docker build -t user-service:v1.0 .'
                        }
                    }
                }
                
                stage('Build product-service') {
                    steps {
                        dir('./Microservices/product-service') {
                            sh 'npx eslint . || true'
                            sh 'docker build -t product-service:v1.0 .'
                        }
                    }
                }

                stage('Build order-service') {
                    steps {
                        dir('./Microservices/order-service') {
                            sh 'npx eslint . || true'
                            sh 'docker build -t order-service:v1.0 .'
                        }
                    }
                }

                stage('Build gateway-service') {
                    steps {
                        dir('./Microservices/gateway-service') {
                            sh 'npx eslint . || true'
                            sh 'docker build -t gateway-service:v1.0 .'
                        }
                    }
                }
            }
        }
        
        stage('Deploy') {
            steps {
                dir('./Microservices'){
                    sh 'docker-compose up -d'    
                }
                        }
        }
    }
    
    post {
        
        success {
            echo 'Build completed successfully!'
            // Optional: You can notify yourself or a team when the build is successful
            emailext(
                subject: "Jenkins Build Success: ${env.JOB_NAME} - ${env.BUILD_NUMBER}",
                body: "The build ${env.BUILD_NUMBER} for ${env.JOB_NAME} has completed successfully.",
                to: "xxxxxxxxx@gmail.com"
            )
        }
        
        failure {
            echo 'Build failed!'
            // Email on failure
            emailext(
                subject: "Jenkins Build Failure: ${env.JOB_NAME} - ${env.BUILD_NUMBER}",
                body: "The build ${env.BUILD_NUMBER} for ${env.JOB_NAME} has failed. Please check Jenkins logs.",
                to: "xxxxxxxx@gmail.com"
            )
        }
        
       
    }
}
