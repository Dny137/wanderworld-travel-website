
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out WanderWorld source code'
                checkout scm
            }
        }

        stage('Validate Files') {
            steps {
                echo 'Validating website files'

                sh '''
                    test -f index.html
                    test -f style.css
                '''
            }
        }

        stage('Build') {
            steps {
                echo 'WanderWorld website build completed'
            }
        }
    }

    post {
        success {
            echo 'WanderWorld pipeline completed successfully!'
        }

        failure {
            echo 'WanderWorld pipeline failed. Check the console output.'
        }
    }
}
