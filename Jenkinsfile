pipeline {
	agent any 
 environment {
	 test = "run"
 }
 tools {
	maven 'maven'
 }
stages {
     stage("Cleanup Workspace"){
        steps {
                cleanWs()
            }

        }
	stage ("test"){
		steps {
			script {
				sh "mvn test"
			}
		}
	}
   }
}
