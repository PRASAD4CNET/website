pipeline {
	agent any
   //agent {label 'slave'}
  //added by avulam for maven tool integration
   tools { 
        maven 'Maven_Home' 
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
	     
	sh 'mvn sonar:sonar -Dsonar.projectKey=test_project -Dsonar.host.url=http://3.97.69.238:9000 -Dsonar.login=ae88e72d47a889eaa8757716193212918f8982e0'
       // sh 'mvn clean install'
	      //sonar:sonar -Dsonar.host.url=http://ec2-18-188-22-235.us-east-2.compute.amazonaws.com:9000 -Dsonar.login=admin -Dsonar.password=admin
	      //sh 'mvn clean install'
      
        //build 'testmvn'
      
      }
    }
		    
	    stage('Pushing nexus') {
		    steps {
			    echo 'Pushing war to s3..'
			  //  sh 'mvn -e clean deploy'
        //sh 'aws s3 ls'
        //sh 'aws s3 cp /var/lib/jenkins/workspace/Maven_pip/target/mywebsiteProject-mywebsiteProject*.war s3://cicd-testings/${BUILD_NUMBER}/'
        //sh 'aws cp 
		    }
	    }
	    
    stage('Pushing war to s3') {
      steps {
        echo 'Pushing war to s3..'
        //sh 'aws s3 ls'
        //sh 'aws s3 cp /var/lib/jenkins/workspace/Maven_pip/target/mywebsiteProject-mywebsiteProject*.war s3://cicd-testings/${BUILD_NUMBER}/'
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
