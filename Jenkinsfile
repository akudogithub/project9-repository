pipeline{
	agent any 
	stages{
	stage('1-version-control'){
		steps{
			checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'Github-id', url: 'https://github.com/akudogithub/project9-repository.git']]])		
		}
	}
	stage('2-code-analysis'){
		steps{
			sh 'sudo systemctl status jenkins'
		}
	}
	stage('3-parallel-job'){
		parallel{
			stage('sub-job1'){
				steps{
					echo 'akudo job1'
					sh 'ps -ef'
				}
			}
			stage('sub-job2'){
				steps{
					sh 'tail -5 /etc/passwd'
					sh 'head -3 /etc/passwd'
				}
			}
		}
	}
	stage('4-code-build'){
		steps{
			sh 'lscpu'
			sh 'lsblk'
		}
	}
}
