pipeline {
  agent none
  options { 
      skipDefaultCheckout() 
  }
  stages{
    stage('SCM operation'){
      agent {label 'SlaveSCMConnected'}
      steps{
        checkout scm
        sh 'mvn clean install'
      }
   }
    stage('Operation without SCM'){
      agent {label 'SlaveWithoutConnectionToSCM'}
      steps{
        mail (to: 'devops@acme.com',
             subject: "Job '${env.JOB_NAME}' (${env.BUILD_NUMBER}) is waiting for input",
            body: "Please go to ${env.BUILD_URL}.");
      }
   }
  }
}
