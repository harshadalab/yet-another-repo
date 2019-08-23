pipeline {
  agent {
    node {
      label 'SonarAndJenkinsSlave'
    }
  }
  
  stages {
    stage('Stage 1') {
      steps {
        echo 'You are in stage 1'
      }
    }
    
    stage('Deploying code') {
      steps {
        echo 'Deployment done'
      }
    }
    
    stage('OnNonDeployableBranch') {
      when { not { expression { env.BRANCH_NAME ==~ '(^hotfix[0-9].{2,4}$)|(^release[0-9].{2,4}$)|(^develop$)' } } }
      steps {
          echo "Code will not be deployed from ${env.BRANCH_NAME} branch"
      }
    }
  }
}
