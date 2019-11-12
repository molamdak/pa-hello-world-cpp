properties([
	pipelineTriggers([pollSCM('H/3 * * * *')])
	])
node(){
	cleanWs()
	checkout scm
	
	
	
        stage('Build') { 
             
                sh 'make'
		 
            }
        
        stage('Test'){
            
                sh "./main" 
            }
        
        stage('Archive') {
            
                archiveArtifacts(artifacts: 'main',fingerprint : true, onlyIfSuccessful : true)

           }
		
}
