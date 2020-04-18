node{
	stage('SCM Checkout') {
	   	git 'https://github.com/aslam843/test-project.git'
	}
	stage('Compile-Package') {
		def path = tool name: 'gradle-6.1', type: 'gradle'
		sh "${path}/gradle build"
	}
	stage('Deploy to Tomcat') {
		echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
		sh "${path}/gradle -version"
	}
}
