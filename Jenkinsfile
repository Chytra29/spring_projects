pipeline {
  agent any
    tools{
          maven 'maven3'
          jdk 'jdk8'
          }
  environment{
         JAVA_BIN='${jdk}/bin'
  }
        stages{
           stage('Building the code'){
              steps{
                 echo "build is in process"
                 echo "${JAVA_BIN}"
  
                 //sh 'mvn clean package'
               }
                       
          }
          
       }


}
