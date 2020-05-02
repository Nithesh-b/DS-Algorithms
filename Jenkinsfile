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
			withCredentials([usernamePassword(credentialsId: 'Github creds', passwordVariable: 'GIT_PASSWORD', usernameVariable: 'GIT_USERNAME')])
			{
			sh '''
		git clone https://github.com/Nithesh-b/lab.git
		cd lab/
		git branch -a
		git checkout firstbranch
		git log --oneline
		git reset HEAD^
		git log --oneline
		#git remote set-url origin git@github.com:nithesh-b/lab.git
		#git push -f origin firstbranch
		git push https://${GIT_USERNAME}:${GIT_PASSWORD}@github.com:nithesh-b/lab.git"
		'''		

	}
}
}
