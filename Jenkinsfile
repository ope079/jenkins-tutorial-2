pipeline{
        agent any
        stages{
            stage('Clone Repository'){
                steps{
                    sh "https://gitlab.com/qacdevops/chaperootodo_client || true"
                }
            }
            stage('Install Docker & Docker compose'){
                steps{
                    sh "curl https://get.docker.com | sudo bash"
                    sh "sudo curl -L https://github.com/docker/compose/releases/download/\${version}/docker-compose-\$(uname -s)-\$(uname -m) -o /usr/local/bin/docker-compose"
                }
            }
            stage('Deploy the application'){
                steps{
                    sh "sudo docker-compose pull && sudo -E DB_PASSWORD=\${DB_PASSWORD} docker-compose up -d"
                }
            }
        }
}
