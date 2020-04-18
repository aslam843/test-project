node{
	stage('stage1') {
	   sh '''echo checkout'''
	   git 'https://github.com/aslam843/test-project.git'
	}
	stage('stage2') {
		def path = tool name: 'gradle-6.1', type: 'gradle'
		sh '''echo build'''
		sh "${path}/gradle build"
	}
	stage('stage3') {
		sh '''echo stage3 steps'''
		sh "java -version"
	}
}
