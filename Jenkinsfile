pipeline {
  options {
	  timeout(time: 1, unit: 'HOURS')
}
  agent any
  stages {
    stage('Code Build and Deploy') {
          steps {
		  timeout(time: 1, unit: 'MINUTES') {
		  sh "echo 'Hello World'"
		  }
	  }
	}
  }
	post {
		success{
			///git branch: 'firstbranch', credentialsId: 'Github creds', url: 'git@github.com/Nithesh-b/lab.git'
                    sh 'git clone https://${USER}:${encodedPass}@github.com/Nithesh-b/lab.git'
		    sh 'git checkout firstbranch'
                    sh 'git add .'
                    sh 'git commit -m "foobar" '
                    sh 'git push'
                
		
	}
}
