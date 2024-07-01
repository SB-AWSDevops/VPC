pipeline {
  agent {
        label 'AGENT-1'
  }

    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
        ansiColor('xterm')
    }

    environment {
     
        nexusUrl = 'nexus.surisetty.online:8081'
    }

  stages {
    stage('Init'){
   steps{
          sh """
                terraform init 
          """
   }
}

   stage('Plan'){
   steps{
          sh """
                terraform plan
          """
   }
}

  }

      post {
        always {
      echo 'I will always say hello again'
      deleteDir()
        }
        success {
      echo 'I will say hello only when success'
        }
        failure {
      echo 'I will say hello only when failure'
        }
      }
}
