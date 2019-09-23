pipeline {
  stage ('SonarQube analysis') {
     steps {
        script {
           STAGE_NAME = 'SonarQube analysis'

           if (BRANCH_NAME == 'develop') {
              echo "In develop branch, dont analyze."
           }
           else { // this is a PR build, run sonar analysis
              withSonarQubeEnv('SonarGate') {
                echo "In branch, need to analyze." 
              }
           }
        }
     }
  }
}
