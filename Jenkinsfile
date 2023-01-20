node {
	docker.image('maven:3-alpine').withRun(' -p 3000:3000 ') {
		stage('Build') {
			def maven_ver = 'M3'
			withEnv( ["PATH+MAVEN=${tool maven_ver}/bin"] ) {
				sh 'mvn -B -DskipTests clean package'
			}
		}

		stage('Test') {
			sh 'mvn test'
		}
	}
}
