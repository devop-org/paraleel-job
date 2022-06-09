
pipeline{
  agent any
  stages{
  	stage('version-control'){
  		steps{
  		checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/devop-org/paraleel-job.git']]])	
  		}
  	}
    stage('parallel-job'){
      parallel{
        stage('sub-job1'){
          steps{
            echo 'action1'
          }
        }
        stage('sub-job2'){
          steps{
            echo 'action2'
          }
        }
        stage('sub-job3'){
            steps{
                echo 'action3'
            }
        }
      }
    }
    stage('codebuild'){
    	steps{
    		sh 'cat /etc/passwd'
    	}
    }
  }
}