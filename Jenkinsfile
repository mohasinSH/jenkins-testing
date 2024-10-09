pipeline {
    agent any  // This runs the pipeline on any available agent

    stages {
        stage('Preparation') {
            steps {
                // Checkout the code from your repository
                git url: 'https://github.com/your-repo/sample-python.git', branch: 'main'
            }
        }

        stage('Run Python Script') {
            steps {
                // Ensure Python is installed and run the script
                sh 'python3 test.py'  // Use 'python' if Python 3 is the default
            }
        }
    }

    post {
        success {
            echo 'The Python script ran successfully!'
        }
        failure {
            echo 'The Python script failed!'
        }
    }
}
