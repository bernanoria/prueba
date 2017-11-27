node {
	
	stage ('Traigo'){

	git 'https://github.com/bernanoria/prueba'

	}
	
	stage('Corro copia'){

		ansiblePlaybook credentialsId: 'jen', extras: 'pathArchivo=holamundo.php', inventory: 'host', playbook: 'copio.yaml', sudoUser: null

	}

	stage('Corro reinicio'){

		if (params.RESTART==true){
			sh 'ansible-playbook reinicio.yaml -i host --private-key ../../.ssh/clave -e service=apache2'

		}
	}	
}