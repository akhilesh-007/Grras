pipeline{
    agent {label 'linux'}
    stages{
        stage("git checkout")
        {
            steps{
                    git url: 'https://github.com/akhilesh-007/Grras.git', branch: 'main'
                 }
          }
        stage("create custom image using dockerfile")
        {
            steps{
                sh "docker build -t webserver ."
            }
        }
       
        stage("create docker container use webserver image")
        {
            steps{
                sh "docker run  --name=mywebserver1 webserver /bin/bash"
            }   
            }
         stage("verify web server running or not ")
        {
            steps{
                sh "docker images"
                sh "docker ps -a"
            }   
            }
    }
}
