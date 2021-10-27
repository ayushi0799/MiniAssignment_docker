node{
        
       stage('SCM checkout') {
               git credentialsId: 'Git-Cred', url: 'https://github.com/ayushi0799/MiniAssignment_docker'
            }
      stage('Build Docker image') {         
           bat 'docker build -t ayushi0799/my-app:2.0.0 .'  
       } 
        stage('Push Docker image') {
          withCredentials([string(credentialsId: 'docker-password', variable: 'DockerHubPassword')]) {
                   bat "docker login -u ayushi0799 -p ${DockerHubPassword}"
           }
          
           bat 'docker push ayushi0799/my-app:2.0.0'
        }
        stage('Deploy'){
                bat 'docker pull ayushi0799/my-app:2.0.0'
                bat 'docker run -p 3000:3000 -d ayushi0799/my-app:2.0.0'
        }
      
       
}
