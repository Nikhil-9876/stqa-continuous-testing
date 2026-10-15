pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Nikhil-9876/stqa-continuous-testing.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'python3 -m pytest test_calculator.py -v'
            }
        }
    }

    post {
        success {
            echo 'All tests passed! Build successful.'
        }
        failure {
            echo 'Tests failed! Fix the defect and push again.'
        }
    }
}
