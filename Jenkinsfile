pipeline {
  agent any
	 
	 stages {
	      stage ('git checkout') {
		       steps {
			       git branch: 'main', url: 'https://github.com/sharanya-09/spark.git' 
				}
			}	
			stage ('build stage') {
			    steps {
				     sh 'mvn clean install'
				}
			}
			stage('SonarQube analysis') {
			steps{
			withSonarQubeEnv('sonarqube-8.9.2') {
			sh "mvn sonar:sonar"
			}
			}
			}
			
			
			stage ('push to artifactory') {
			    steps {
				     sleep 15
				}
			}
			}
		}
