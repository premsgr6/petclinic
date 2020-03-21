pipeline {
	agent any
    stages {
	     stage('SCM') {
            steps {
                script {
                    git credentialsId: 'GIT-PASSWD', url: 'https://github.com/premsgr6/petclinic.git'
                }
            }
        }
	    
        stage('Build on k8 ') {
            steps {           
                        sh 'pwd'
                        sh 'cp -R helm/* .'
		        sh 'ls -ltr'
                        sh 'pwd'
                        sh '/usr/local/bin/helm upgrade --install petclinic-app petclinic  --set image.repository=registry.hub.docker.com/premsgr6/petclinic --set image.tag=1'
              			
            }           
        }
    }
}
