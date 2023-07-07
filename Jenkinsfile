pipeline {
    agent any
    stages {
        stage("Verify SSH connection to server") {
            steps {
                sshagent(credentials: ['virtualbox-ubuntu']) {
                    sh '''
                        ssh -o StrictHostKeyChecking=no ubuntu@192.168.56.101 whoami
                        docker info
                        docker version
                        docker compose version
                        docker images
                        docker ps -a
                    '''
                }
            }
        }        
        
            
       
    }

}
