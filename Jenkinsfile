node {
	checkout scm
	docker.image('maven:3.8.7-eclipse-temurin-11').withRun(' -p 3000:3000 -v /root/.m2:/root/.m2 ') {
		stage('Build') {
			sh 'mvn -B -DskipTests clean package'
		}

		stage('Test') {
			sh 'mvn test'
		}
	}
}
