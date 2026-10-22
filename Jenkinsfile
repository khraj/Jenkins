pipeline{
    agent {
        node {
            label 'agent-1'
        }
    }
    options {
        timeout(time: 10, unit: 'SECONDS')
    }
    environment {
        COURSE = 'Jenkins'
    }
    stages{
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
                script {
                    sh """

                        echo "Testing..."
                        echo "course = $COURSE"
                        env
                        sleep 10

                    """
                }
                
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
    post {
        always {
            echo "Cleaning up..."
            cleanWs()
        }
        success {
            echo "Build succeeded!"
        }
        failure {
            echo "Build failed!"
        }
    }
}