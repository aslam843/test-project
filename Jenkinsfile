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
		sh "java -version"
	}
	post {
		always {
		    emailext body: """<p>Check console output at <a href="${env.BUILD_URL}">${env.JOB_NAME}</a></p>""", recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: "Job '${env.JOB_NAME} ${env.BUILD_NUMBER}'"
		}
    	}
}
