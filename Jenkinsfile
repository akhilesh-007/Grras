pipeline{
    agent {label 'Linux'}
    stages{
        stage("git checkout")
        {
            steps{
                    git url: 'https://github.com/akhilesh-007/jaipur123.git', branch: 'dev'
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
                sh "docker run  --name=mywebserver webserver /bin/bash"
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
