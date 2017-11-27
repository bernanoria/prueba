node {

	def workingDir = pwd()
	
	stage('Corro copia'){

		dir("${workingDir}@script") {
		
			sh 'ansible-playbook copio.yaml -i host --private-key ../../.ssh/clave -e pathArchivo=${archivo}'
			
		}
	}

	stage('Corro reinicio'){
		dir("${workingDir}@script") {

			if (params.RESTART==true){
				sh 'ansible-playbook reinicio.yaml -i host --private-key ../../.ssh/clave -e service=${servicio}'

			}
		}
	}	
}
