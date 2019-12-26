pipeline {
  agent any
    tools{
          maven 'maven3'
          //jdk 'jdk8'
          }
        stages{
           stage('Building the code'){
              steps{
                 echo "build is in process"
                 echo "${PATH}"
                 echo "${WORKSPACE}"
                 //sh 'mvn clean package'
               }
             }
          
          stage('Starting the microservice'){
            steps{
              echo "Hello"
              //sh 'java -jar **/target/*.jar'
            }
          }
          
       }


}
