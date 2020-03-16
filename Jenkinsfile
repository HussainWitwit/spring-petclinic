pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh './mvnw package' 
            }
        }
        stage('Test'){
            steps {
                sh './mvnw test'
            }
        }
        stage('Package'){
            steps{
                sh './mvnw package'
            } 
        }
        stage('Deploy'){
            steps{
                echo 'Deploy'
            }
        }
    }
    post {
    success {
      slackSend (color: '#00FF00', message: "SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})");
            }
    }
}
