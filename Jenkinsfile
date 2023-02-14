pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                
                sh 'sudo apt-get update'
                sh 'sudo apt-get install -y cmake'
                sh 'cmake .'
                sh 'make'
                echo 'Build Stage Successful'
            }
        }

        stage('Test') {
            steps {
                
                sh 'ctest --output-on-failure'
                echo 'Test Stage Successful'
            }
        }

        stage('Deploy') {
            steps {
                
                sh 'scp ./myapp user@server:/path/to/deploy'
                echo 'Deployment Successful'
            }
        }
    }

    post {
      failure{
        echo 'Pipeline failed'
      }
        
    }
}
