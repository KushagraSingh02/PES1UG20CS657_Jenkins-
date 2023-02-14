pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                
                sh 'g++ -o PES1UG20CS657 PES1UG20CS657.cpp'
                build job: 'PES1UG20CS657-1'
                echo 'Build Stage Successful'
            }
        }

        stage('Test') {
            steps {
                
                sh './PES1UG20CS657'
                echo 'Test Stage Successful'
            }
        }

        stage('Deploy') {
            steps {
                
                
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
