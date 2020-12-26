pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
        /*
        build 'testmvn'
      */
        mvn clean install
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
