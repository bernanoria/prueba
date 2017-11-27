node {

	def workingDir = pwd()
	
 	stage('PRINT'){
		def output = sh returnStdout: true, script: "ls -la .."
		println output
		println "---------------------------"
		def output2 = sh returnStdout: true, script: "ls -la"
		println output2
		
 	}
	
	stage('Corro copia'){

		dir("${workingDir}") {
		
			sh 'ansible-playbook copio.yaml -i host --private-key ../../.ssh/clave -e pathArchivo=${archivo}'
			
		}
	}

	stage('Corro reinicio'){

		if (params.RESTART==true){
			sh 'ansible-playbook reinicio.yaml -i host --private-key ../../.ssh/clave -e service=${servicio}'

		}
	}	
}
