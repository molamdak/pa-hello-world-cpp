properties([
	pipelineTriggers([pollSCM('H/3 * * * *')])
	])
node(){
	cleanWs()
	checkout scm
	
	
	
        stage('Build') { 
             
                sh 'make'
		sh "./main" 
            }
        
        stage('Test'){
            
                sh 'make check' 
            }
        
        stage('Archive') {
            
                archiveArtifacts(artifacts: 'main',fingerprint : true, onlyIfSuccessful : true)

           }
		
}
