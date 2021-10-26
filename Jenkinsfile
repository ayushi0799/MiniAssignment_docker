node{
        def repo;
        stage('Test') {
               git credentialsId: '3dc64b55-a9c9-43ca-9291-42d88d990dc8', url: 'https://github.com/ayushi0799/MiniAssignment_docker'
            }
 
      
      stage('Build image') {         
       
            repo = docker.build("ayushi0799/app")    
       }   
      

       stage('Push image to DockerHub') {
             
             docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {            
             repo.push("${env.BUILD_NUMBER}")            
             repo.push("latest")        
              
             }    
           
    
        
        stage('Build Docker image') {
                echo 'Building'
            }
        stage('Pull') {
                echo 'Testing'
            }
       
}
