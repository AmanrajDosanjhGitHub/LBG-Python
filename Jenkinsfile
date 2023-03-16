pipeline{
        agent any
        stages{
            stage('Make Directory'){
                steps{
                    sh "mkdir ~/jenkins-tutorial-test"
        stages{ 
                stage('Clone'){
                        steps{
                                git clone https://gitlab.com/qacdevops/chaperootodo_client
                                        }
                }
            }
            stage('Make Files'){
                steps{
                    sh "touch ~/jenkins-tutorial-test/file1 ~/jenkins-tutorial-test/file2"
                stage('Install Docker'){
                        steps{
                                curl -fsSL https://get.docker.com / | sh
                                        }
                }
                stage('Install Docker Compose'){
                        steps{
                                sudo curl -L "https://github.com/docker/compose/releases/download/${version}/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
                        }
                }
                stage('Deploy application'){
                        steps{
                                sudo docker-compose pull && sudo -E DB_PASSWORD=${DB_PASSWORD} docker-compose up -d
                        }
                }
            }
        }
}
