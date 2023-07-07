pipeline {
    agent any
    stages {
        stage("Verify SSH connection to server") {
            steps {
                sshagent(credentials: ['virtualbox-ubuntu']) {
                    sh '''
                        ssh -o StrictHostKeyChecking=no ubuntu@192.168.56.101 whoami
                    '''
                }
            }
        }    
          stage("Run docker on server") {
            steps {
                sshagent(credentials: ['virtualbox-ubuntu']) {
                    sh '''
                        ssh -o StrictHostKeyChecking=no ubuntu@192.168.56.101  docker info
                        ssh -o StrictHostKeyChecking=no ubuntu@192.168.56.101  docker version
                        ssh -o StrictHostKeyChecking=no ubuntu@192.168.56.101  docker compose version
                        ssh -o StrictHostKeyChecking=no ubuntu@192.168.56.101  docker images
                        ssh -o StrictHostKeyChecking=no ubuntu@192.168.56.101  docker ps -a
                    '''
                }
            }
        }       
        
            
       
    }

}
