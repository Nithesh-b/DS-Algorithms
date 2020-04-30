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
		  sh "sleep 2h"
		  }
	  }
	}
  }
	post {
		failure{
			git branch: 'firstbranch', credentialsId: 'Github creds', url: 'git@github.com/Nithesh-b/lab.git'
			sh '''	
			git pull
			git checkout firstbranch
			git reset HEAD^
			git remote set-url origin git@github.com:nithesh-b/lab.git
			git push -f origin firstbranch --no-verify
			'''
		}
	}
}
