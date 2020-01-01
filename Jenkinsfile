pipeline {
  agent any
    tools{
          maven 'maven3'
          jdk 'jdk8'
        
          }
  
        stages{
           stage('Building the code'){
              steps{
                 echo "build is in process"
                 sh 'mvn clean package'
               }
                       
          }
          
       }


}
