pipeline{
  stage('SonarQube analysis'){
    steps{
      script{
        STAGE_NAME='SonarQube analysis'if(BRANCH_NAME=='develop'){
          echo"In develop branch, dont analyze."
        }else{
          //thisisaPRbuild,
          runsonaranalysiswithSonarQubeEnv('SonarGate'){
            echo"In branch, need to analyze."
          }
        }
      }
    }
  }
}

