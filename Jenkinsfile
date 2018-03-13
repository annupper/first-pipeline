node {
	def mvnHome;
	stage ('Init') {
		git 'https://github.com/annupper/first-pipeline.git'
		mvnHome = tool 'Maven3.5.3'
	}
	stage ('Build') {
		//only for unix
		sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
	}
	stage ('Results') {
		junit '**/target/surefire-reports/TEST-*.xml'
		archive 'target/*.jar'
	}
}