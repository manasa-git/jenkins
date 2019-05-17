
node {

   stage('checkout') {
    
   git 'https://github.com/manasa-git/jenkins.git'
    
    }


    def project_path = "spring-boot-samples/spring-boot-sample-atmosphere"

    dir (project_path) {
        stage('compile_test_package') {

        sh 'mvn clean package'
        }

        stage('archival') {

        archiveArtifacts 'target/*.jar'    
        }
       
        stage('Email_notification'){

        mail bcc: '', body: '''Hi, Welcome to Jenkins server.
	     Thanks,
	     Manasa.''', cc: '', from: '', replyTo: '', subject: 'build notification', to: 'meetmanasa.iiit@gmail.com'
	
        }
    }
}
