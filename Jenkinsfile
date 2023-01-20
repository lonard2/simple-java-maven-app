node {
	docker.image('maven:3-alpine').withRun(' -p 3000:3000 ') {
		stage('Build') {
			sh 'mvn -B -DskipTests clean package'
		}

		stage('Test') {
			sh 'mvn test'
		}
	}
}
