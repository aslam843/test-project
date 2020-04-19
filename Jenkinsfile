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
	stage('Email Notification') {
		mail bcc:"",body: """Check console output at ${env.BUILD_URL}console""",cc:"",from:"enroll@1kosmos.com",to:"aslam@1kosmos.com",subject: "Job '${env.JOB_NAME} ${env.BUILD_NUMBER}'"
	}	
}
