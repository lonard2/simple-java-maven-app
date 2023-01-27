node {
	checkout scm
	docker.image('maven:3.8.7-eclipse-temurin-11').inside(' -p 3000:3000  -v $HOME/.m2:/root/.m2 ') {
		stage('Build') {
			sh 'mvn -B -DskipTests clean package'
		}

		stage('Test') {
			sh 'mvn test'
		}

		stage('Manual Approval') {
			input message: 'Lanjutkan ke tahap Deploy?'
		}

		stage('Deploy') {
			sh './jenkins/scripts/deliver.sh'
			
			echo 'Aplikasi telah berhasil dijalankan!'

			sleep 60

			echo 'Proses deployment aplikasi Java App akan segera ditutup.'
			echo 'Menutup aplikasi Java App...'
		}
	}
}
