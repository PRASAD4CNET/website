pipeline {
   agent {label 'slave'}
  //added by avulam for maven tool integration
   tools { 
        maven 'Maven' 
       // jdk 'jdk8' 
    }
  
  /* triggers added by prasad
  triggers {
	//Execute every minute
cron('* * * * *')
}
  triggers end prasad*/
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
	      echo " Nothing to change"

        sh 'mvn clean install sonar:sonar -Dsonar.host.url=http://ec2-18-188-22-235.us-east-2.compute.amazonaws.com:9000 -Dsonar.login=admin -Dsonar.password=admin'
	      //sh 'mvn clean install'
      
        //build 'testmvn'
      
      }
    }
    stage('Pushing war to s3') {
      steps {
        echo 'Pushing war to s3..'
        sh 'aws s3 ls'
        sh 'aws s3 cp /var/lib/jenkins/workspace/Maven_pip/target/mywebsiteProject-mywebsiteProject*.war s3://cicd-testings/${BUILD_NUMBER}/'
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
