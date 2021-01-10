pipeline {

  agent any
  environment {
    NEW_VERSION = '1.0.1'
  }

  stages {
  
    stage("build") {
      steps {
        echo 'Building the application...'
        echo "Building version ${NEW_VERSION}"
      }
    }
    
    stage("test") {
      steps {
        echo 'Testing the application...'
      }
    }
    
    stage("Deploy") {
      steps {
        echo 'Deploying the application...'
        withCredentials([
          usernamePassword(credentialsId: 'server-credentials', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')
        ]) {
          sh 'echo username is $USERNAME and password is $PASSWORD '
        }
      }
    }
    
  }
  
}
