pipeline {
	agent any 
 environment {
	 test = "run"
	 ECR_REPO_URL = "520385696955.dkr.ecr.ap-south-1.amazonaws.com"
         ECR_REPO_NAME = "web-app"
         AWS_REGION = "ap-south-1"
 }
 tools {
	maven 'maven'
 }
 parameters {
        string(name: 'IMAGE_TAG', defaultValue: '', description: 'image tage')
    }

stages {
	stage ("Test"){
		steps {
			script {
				sh "mvn test"
			}
		}
     }
     stage('Sonar code quality analysis') {
            steps {
                script {
                    def scannerHome = tool 'sonar-scaner'
                    withSonarQubeEnv('sonar') {
                        sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=complete-prodcution-e2e-pipeline -Dsonar.language=java  -Dsonar.java.binaries=target/classes  -Dsonar.sourceEncoding=UTF-8"
                    }
                }
            }
     }
     
     stage("Cleanup Workspace"){
        steps {
                cleanWs()
            }

        }
   }
}
