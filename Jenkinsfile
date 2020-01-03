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
          
          stage('Uploading to Artifactory')
          {
            steps{
               rtUpload (
            serverId: 'Artifactory-1',
           spec: '''{
            "files": [
            {
              "pattern": "${WORKSPACE}/target/*.jar",
              "target": "demo_maven/"
            }
         ]
    }''',
 
   
)
            }
          }
          stage('Download from Artifactory for deployment')
          {
            steps{
              rtDownload(
                serverId: 'Artifactory-1'
                 spec: '''{
                "files": [
               {
              "pattern": "demo_maven/*.jar",
              "target": "/var/lib/jenkins/workspace/deploy_springboot/",
               }
            ]
        }''',
              )
            }
          }
               
          
            }
        }             

