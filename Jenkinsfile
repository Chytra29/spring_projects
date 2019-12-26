pipeline {
  agent any
    tools{
          maven 'maven3'
          jdk 'jdk8'
        
          }
  environment{
         project='springboot'
         
         
  }
        stages{
           stage('Building the code'){
              steps{
                 echo "build is in process"
                 echo "${project}"
                sh '${jdk}/bin/java -version'
                
  
                 //sh 'mvn clean package'
               }
                       
          }
          
       }


}
