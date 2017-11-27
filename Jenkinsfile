node {
	
	stage('Corro copia'){

		sh 'ansible-playbook copio.yaml -i host --private-key ../../.ssh/clave -e pathArchivo=holamundo.php'

	}

	stage('Corro reinicio'){

		if (params.RESTART==true){
			sh 'ansible-playbook reinicio.yaml -i host --private-key ../../.ssh/clave'

		}
	}	
}