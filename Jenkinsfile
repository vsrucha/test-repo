pipeline {
    agent any  

    environment {
        STAGING_SERVER = 'staging.yourdomain.com'  // Placeholder staging server address
        PROD_SERVER = 'prod.yourdomain.com'       // Placeholder production server address
    }

    stages {
        stage('Build') {
            steps {
                echo "Building the project..."
                sh 'mvn clean install'  
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                sh 'mvn test' 
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "Deploying to Staging server: ${STAGING_SERVER}"
                sh "echo Deploying build to ${STAGING_SERVER}"  // Showcasing deployment
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying to Production server: ${PROD_SERVER}"
                sh "echo Deploying build to ${PROD_SERVER}"  //Showcasing deployment
            }
        }
    }

    post {
        success {
            echo "Build and deployment completed successfully!"
        }
        failure {
            echo "Build or deployment failed!"
        }
    }
}

