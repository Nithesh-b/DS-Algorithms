pipeline {

  agent any
  stages {
    stage('Code Build and Deploy') {
          steps {
		  sh "echo 'Hello World'"
		  }
	}
  }
	post {
		success{
			sh '''
			git pull  https://github.com/Nithesh-b/lab.git master
			git checkout master
			git reset HEAD^
			git remote set-url origin git@github.com:nithesh-b/lab.git
			git push -f origin master --no-verify
			'''
		}
	}
}
