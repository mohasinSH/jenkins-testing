pipeline {
    agent any
    stages {
        stage('CheckOuts') {
            steps {
                // Cloning the specified GitHub repository
                git branch: 'main', url: 'https://github.com/mohasinSH/jenkins-testing.git'
            }
        }
        stage('Builds') {
            steps {
                // This stage can contain your build steps (if any)
                echo 'Building the project...'
                // You can replace this with actual build commands if needed
            }
        }
        stage('Test') {
            steps {
                // Running the Python test script
                echo 'Running tests...'
                sh 'python3 test.py'  // Ensure the test.py script is executable
            }
        }
        stage('Deploy') {
            steps {
                // This stage can contain your deployment steps (if any)
                echo 'Deploying the project...'
                // You can replace this with actual deployment commands if needed
            }
        }
    }
    post {
        success {
            echo 'Pipeline succeeded!'
            emailext (
                to: 'ismail4111969@gmail.com',
                subject: "Successful Build: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """<p>Build successful!</p>
                          <p>Job Name: ${env.JOB_NAME}</p>
                          <p>Build Number: ${env.BUILD_NUMBER}</p>
                          <p>View Build: <a href="${env.BUILD_URL}">${env.BUILD_URL}</a></p>""",
                mimeType: 'text/html'
            )
        }
        failure {
            echo 'Pipeline failed!'
            emailext (
                to: 'ismail4111969@gmail.com',
                subject: "Failed Build: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """<p>Build failed!</p>
                          <p>Job Name: ${env.JOB_NAME}</p>
                          <p>Build Number: ${env.BUILD_NUMBER}</p>
                          <p>View Build: <a href="${env.BUILD_URL}">${env.BUILD_URL}</a></p>""",
                mimeType: 'text/html'
            )
        }
        always {
            echo 'Pipeline completed.'
        }
    }
}
