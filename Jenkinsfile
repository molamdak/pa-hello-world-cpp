properties([
	pipelineTriggers([pollSCM('H/3 * * * *')])
	])
node(){
	cleanWs()
	checkout scm
	
	
	stages {
        stage('Build') { 
            steps { 
                sh 'make'
		sh "./main" 
            }
        }
        stage('Test'){
            steps {
                sh 'make check' 
            }
        }
        stage('Archive') {
            steps {
                archiveArtifacts(artifacts: 'main',fingerprint : true, onlyIfSuccessful : true)

            }
        }
    
     }
		
}
