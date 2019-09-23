pipeline {
  stage ('SonarQube analysis') {
     steps {
        script {
           STAGE_NAME = 'SonarQube analysis'

           if (BRANCH_NAME == 'develop') {
              echo "In 'develop' branch, don't analyze."
           }
           else { // this is a PR build, run sonar analysis
              withSonarQubeEnv('SonarGate') {
                 sh "../../../sonar-scanner-2.9.0.670/bin/sonar-scanner"   
              }
           }
        }
     }
  }
}
