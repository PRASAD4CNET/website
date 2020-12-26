pipeline {
  agent any
  tools{
    maven 'Maven'
  
  }
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
        /*
        build 'testmvn'
      */
        maven clean install
      }
    }
    stage('Test') {
      steps {
        echo 'Testing..'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying....'
      }
    }
  }
}
