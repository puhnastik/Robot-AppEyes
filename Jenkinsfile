pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building ...'
        gitlabCommitStatus(name: 'Build') {
          echo 'Building for GitLab'
        }
        
      }
    }
    stage('Deploy to QA') {
      steps {
        echo 'Deploying to QA ...'
      }
    }
    stage('Test on QA') {
      steps {
        echo 'Testing on QA ...'
      }
    }
    stage('Deploy to Integration') {
      steps {
        echo 'Deploying to Integration'
      }
    }
    stage('Test on Integration') {
      steps {
        echo 'Testing on Integration'
      }
    }
    stage('Deploy to UAT') {
      steps {
        parallel(
          "Deploy to UAT": {
            echo 'Deploying to UAT'
            
          },
          "Deploy to Perf": {
            echo 'Deploying to Perf ...'
            script {
              
            }
            
            
          }
        )
      }
    }
    stage('Test on UAT') {
      steps {
        parallel(
          "Test on UAT": {
            echo 'Testing on UAT'
            
          },
          "Test on Perf": {
            echo 'Testing on Perf ...'
            
          }
        )
      }
    }
    stage('Release') {
      steps {
        echo 'Releasing ...'
      }
    }
  }
}