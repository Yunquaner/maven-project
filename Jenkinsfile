pipeline {
  agent any
  stages {
    stage("Build"){
      steps {
        sh 'mvn clean package'
      }
      post {
        success {
          echo '开始存档...'
          archiveArtifacts artifacts: '**/target/*.war'
         }
      }
      
      stage("Deploy-to-staging"){
        build job:'deploy-to-staging'
      }
      
    }
  }
}
