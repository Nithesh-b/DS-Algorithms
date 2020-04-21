pipeline {
  options {
	  timeout(time: 1, unit: 'HOURS')
}
  agent any
  stages {
    stage('Code Build and Deploy') {
          steps {
		  sh "echo 'Hello World'"
		  sh "sleep 2h"
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
