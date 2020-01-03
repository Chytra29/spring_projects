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
               def server = Artifactory.server "Artifactory-1"
                  def uploadSpec =
            '''{
            "files": [
                {
                    
                    "pattern": "**/target/*.jar",
                    "target": ""demo_maven""
                }
                
            ]
        }'''
 
    
        server.upload(uploadSpec)
            }
          }
          
               
          stage ('Publish build info') {
            steps {
                rtPublishBuildInfo (
                    serverId: "Artifactory-1"
                )
            }
        }             
          
          
       }


}
