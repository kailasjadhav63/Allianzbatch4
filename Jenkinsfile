pipeline {
    agent any

    stages {
        stage('Install and Start new HTTPD Server') {
            steps {
                // Update system, install HTTPD (Apache) server, and start the service
                sh '''
                sudo apt-get update -y
                sudo apt-get install apache2 -y
                sudo systemctl start apache2
                sudo systemctl enable apache2
                '''
            }
        }
        stage('Check HTTPD Server Status') {
            steps {
                // Check if the HTTPD (Apache) server is running
                sh '''
                if systemctl is-active --quiet apache2; then
                    echo "HTTPD server is running."
                else
                    echo "HTTPD server is NOT running!"
                    exit 1
                fi
                '''
            }
        }
        stage('Website is Live') {
            steps {
                // Display a message indicating the website is live
                echo "Your website is live now!"
            }
        }
    }

    post {
        always {
            // Optional: Cleanup or any post-build actions can be added here
            echo 'Pipeline execution completed.'
        }
    }
}
