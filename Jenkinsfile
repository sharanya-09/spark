pipeline {
	agent {
	       label 'tomcat-slave'
		   }
	
	stages {
        stage('GIT checkout') {
            steps {
    git branch: 'main', url: 'https://github.com/sharanya-09/spark.git'
            }
        }
	
        stage('Build stage') {
            steps {
			   sh 'mvn clean install'
			}
        }

        stage('Push to Artifactory') {
            steps {
			   sleep 15
			}
	    }
	
	    stage('Deploy stage') {
            steps {
			   sh 'sudo cp /home/ec2-user/jenkins/workspace/pipeline2/target/*.war /home/ec2-user/apache-tomcat-10.0.22/webapps/'
            }		  	
	    }
    }
	
}

