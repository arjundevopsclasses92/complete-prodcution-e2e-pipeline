pipeline {
	agent any 
 environment {
	 test = "run"
 }
 tools {
	maven 'maven'
 }
stages {
	stage ("test"){
		steps {
			script {
				sh "mvn test"
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
