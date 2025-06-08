pipeline {
	agent any 
 environment {
	 test = "run"
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
