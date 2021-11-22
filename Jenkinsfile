pipeline {
    agent any
    environment  {

      registryCredential = 'dockerhub'

  
}

     stages {

       stage('Build'){

            steps {


           sh 'docker build -t devadeel/test-node-app .'
}
       }

    stage ('Test'){

       steps{
           sh 'docker containber stop node'
           sh 'docker container rm node'
         sh 'docker container run -p 8001:8080 --name node -d devadeel/test-node-app'
       

}
}

     stage('Publish'){

       steps{

         script {

         docker.withRegistry( '', registryCredential ){
         sh 'docker push devadeel/test-node-app:latest'
     }
}
}
    
}

}
  
}
