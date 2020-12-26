pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building..'

        sh '/opt/maven/apache-maven-3.6.3/bin/mvn clean install'
      
        //build 'testmvn'
      
      }
    }
    stage('Pushing war to s3') {
      steps {
        echo 'Pushing war to s3..'
        sh 'aws s3 ls'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying....'
      }
    }
  }
}
