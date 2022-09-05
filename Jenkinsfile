pipeline{
	agent any
	stages{
		stage('git-clone'){
      		steps{
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-id', url: 'https://github.com/team3Group2EtechApp/etechAppParallelJob.git']]])
      }
    }
    	stage('1-first parallel job'){
      	parallel{
        stage('Phil-actions'){
          steps{
            sh 'bash -x /var/lib/jenkins/workspace/etechAppParallelJob/phil.sh'
          }
        }
        stage('abisola'){
          steps{
            sh 'bash -x /var/lib/jenkins/workspace/etechAppParallelJob/abisola.sh'
          }
        }
	}
}
}
}