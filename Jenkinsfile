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
                echo "In 'develop' branch, need to analyze." 
              }
           }
        }
     }
  }
}
