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
            Steps{
               def server = Artifactory.server "Artifactory-1"
               rtUpload (
                serverId: 'Artifactory-1',
                 spec: '''{
                 "files": [
               {
              "pattern": "**/target/*.jar",
              "target": "demo_maven"
            }
         ]
    }''',
 
    
)
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
