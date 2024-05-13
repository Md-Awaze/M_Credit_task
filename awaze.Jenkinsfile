pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Building using Maven..."
                
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Running tests using JUnit and Selenium..."
                
            }
            post {
                always {
                    emailext (
                        to: 'awazemohommed@gmail.com',
                        subject: "Jenkins Build: ${currentBuild.fullDisplayName}",
                        body: """<p>Stage 'Unit and Integration Tests' completed with status ${currentBuild.result}</p>
                                 <p>Check console output at ${env.BUILD_URL} to view the results.</p>""",
                        attachLog: true
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Analyzing code with SonarQube..."
                
            }
        }
        stage('Security Scan') {
            steps {
                echo "Conducting security scan with OWASP ZAP..."
                
            }
            post {
                always {
                    emailext (
                        to: 'awazemohommed@gmail.com',
                        subject: "Jenkins Build: ${currentBuild.fullDisplayName}",
                        body: """<p>Stage 'Security Scan' completed with status ${currentBuild.result}</p>
                                 <p>Check console output at ${env.BUILD_URL} to view the results.</p>""",
                        attachLog: true
                    )
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Deploying to AWS EC2 Staging..."
                
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests in staging environment..."
                
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying to AWS EC2 Production..."
                
            }
        }
    }
}
