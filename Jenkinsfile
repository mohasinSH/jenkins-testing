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
        always {
            echo 'Pipeline completed.'
        }
    }
}
