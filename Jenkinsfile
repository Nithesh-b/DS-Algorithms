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
				git pull  https://github.com/Nithesh-b/lab.git master
				git checkout master
				git reset HEAD^
				#git remote -v
				git remote set-url origin git@github.com:nithesh-b/lab.git
				git push -f origin master --no-verify
                
		
	}
}
}
