pipeline {

  agent any
  stages {
    stage('Code Build and Deploy') {
          steps {
		  sh "echo 'Hello World'"
		  sh not_working
		  }
	}
  }
	post {
		failure{
			sh '''
			git pull  https://github.com/Nithesh-b/lab.git firstbranch
			git checkout firstbranch
			git reset HEAD^
			git remote set-url origin git@github.com:nithesh-b/lab.git
			git push -f origin firstbranch --no-verify
			'''
		}
	}
}
