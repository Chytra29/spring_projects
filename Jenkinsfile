pipeline {
  agent any
    tools{
          maven 'maven3'
          
          }
  environment{
         project=springboot
  }
        stages{
           stage('Building the code'){
              steps{
                 echo "build is in process"
                 echo "${project}"
                 sh 'java --version'
  
                 //sh 'mvn clean package'
               }
                       
          }
          
       }


}
