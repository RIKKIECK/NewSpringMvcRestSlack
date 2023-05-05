pipeline {
    agent any
        stages {
        stage('Initialize'){
            steps{
                echo "Esta es el inicio"
            }
        }
        stage('Build') {
            steps {
                sh 'mvn -B package'
            
            }
        }
            
        stage('Test') {
            steps {
                 sh "mvn clean verify" 
            
            }
        } 
     }
     post {
    always {
      script {
        def slackChannel = '#jenkinsdevops'
        def slackMessage = 'Build finished successfully!'
        slackSend (channel: slackChannel, message: slackMessage)
      }
    }
  }
    
    
    
}
