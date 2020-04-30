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
withCredentials([usernamePassword(credentialsId: 'Github creds', usernameVariable: 'USER', passwordVariable: 'PASS')]) {
                    script {
                        env.encodedPass=URLEncoder.encode(PASS, "UTF-8")
                    }
                    sh 'git clone https://${USER}:${encodedPass}@github.com/Nithesh-b/lab.git'
		    sh 'git checkout firstbranch'
                    sh 'git add .'
                    sh 'git commit -m "foobar" '
                    sh 'git push'
                } 
		
	}
}
