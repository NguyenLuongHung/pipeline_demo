pipeline {

  agent any
  parameters {
    choice(name: 'VERSION', choices: ['1.1.0', '1.1.1', '1.1.2'], description: '')
    booleanParam(name: 'executeTests', defaultValue: false, description: '')
  }

  stages {
  
    stage("build") {
      steps {
        echo 'Building the application...'
      }
    }
    
    stage("test") {
      when {
        expression {
          params.executeTests
        }
      }
      steps {
        echo 'Testing the application...'
      }
    }
    
    stage("deploy") {
      steps {
        echo 'Deploying the application...'
        echo "deploying version ${param.VERSION}"
      }
    }
    
  }
  
}
