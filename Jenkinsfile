node{
	stage('stage1') {
	   sh '''echo stage1 steps'''
	   git 'https://github.com/aslam843/test-project.git'
	}
	stage('stage2') {
		def path = tool name: 'gradle-6.1', type: 'gradle'
		sh '''echo stage2 steps'''
		sh "${path}/gradle -version"
	}
	stage('stage3') {
		sh '''echo stage3 steps'''
		sh "java -version"
	}
}
