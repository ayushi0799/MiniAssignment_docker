node{
        
       stage('SCM checkout') {
               git credentialsId: '3dc64b55-a9c9-43ca-9291-42d88d990dc8', url: 'https://github.com/ayushi0799/MiniAssignment_docker'
            }
      stage('Build Docker image') {         
       
           bat 'docker build -t ayushi0799/app:2.0.0 .'  
       } 
        stage('Push Docker image') {
           withCredentials([string(credentialsId: 'dockerPassword', variable: 'DockerHubPassword')]) {
                   bat "docker login -u ayushi0799 -p ${DockerHubPassword}"
           }
          
           bat 'docker push ayushi0799/app:2.0.0'
        }
      
       
}
