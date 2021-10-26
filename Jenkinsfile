node{
        stage('Test') {
               git credentialsId: '3dc64b55-a9c9-43ca-9291-42d88d990dc8', url: 'https://github.com/ayushi0799/MiniAssignment_docker'
            }
        stage('mvn packages'){
                def mvnHome = tool name: 'maven-3', type: 'maven'
                def mvnCMD = "${mvnHome}/bin/mvn"
                sh "${mvnCMD} clean package"
        }
      
        
        stage('Build') {
                echo 'Building'
            }
        stage('Pull') {
                echo 'Testing'
            }
       
}
