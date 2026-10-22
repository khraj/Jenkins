pipeline{
    agent {
        node {
            label 'agent-1'
        }
    }
    stages{
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
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
            sh "rm -rf /home/ec2-user/jenkins/workspace/myproject/*"
        }
        success {
            echo "Build succeeded!"
        }
        failure {
            echo "Build failed!"
        }
    }
}