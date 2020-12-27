pipeline {
  agent any
  //added by avulam for maven tool integration
   tools { 
        maven 'Maven' 
       // jdk 'jdk8' 
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }
      //added by avulam for maven tool integration end

    stage('Build') {
      steps {
        echo 'Building..'

        sh 'mvn clean install'
      
        //build 'testmvn'
      
      }
    }
    stage('Pushing war to s3') {
      steps {
        echo 'Pushing war to s3..'
        sh 'aws configure'
        sh 'AKIAVARP4XQQOFIHLAR2'
        sh 'wNPSyO4eNyok+/yToWagzD04FbjjpzIkwgbH6LLF'
        //sh 'aws cp 
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying....'
      }
    }
  }
}
