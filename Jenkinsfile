node{
	stage('SCM Checkout') {
	   	git 'https://github.com/aslam843/test-project.git'
	}
	stage('Compile-Package') {
		def path = tool name: 'gradle-6.1', type: 'gradle'
		sh "${path}/gradle build"
	}
	stage('Deploy to Tomcat') {
		sshagent(['devconsole']) {
                sh "ssh -i /opt/1kosmos/DEVBlockID.pem -o StrictHostKeyChecking=no -o 'ProxyCommand=ssh -o StrictHostKeyChecking=no -i /opt/1kosmos/DEVBlockID.pem -W %h:%p -q ec2-user@ec2-13-233-92-192.ap-south-1.compute.amazonaws.com' ec2-user@172.16.246.163 'sudo sh system-info.sh'"
            }
	}
}
