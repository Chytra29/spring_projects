pipeline {
  agent any
    tools{
          maven 'maven3'
          jdk 'jdk8'
        
          }
  
        stages{
          
          
          
             stage('Artifactory info'){
              steps{
                 rtServer (
                 id: 'Artifactory-1',
                 url: 'http://35.188.102.0:8081//artifactory',
                 username: 'admin',
                 password: 'password'
    
                           )
                
                 rtMavenDeployer (
                    id: "MAVEN_DEPLOYER",
                    serverId: "Artifactory-1",
                    releaseRepo: "libs-release-local",
                    snapshotRepo: "libs-snapshot-local"
                     )
                
                rtMavenResolver (
                    id: "MAVEN_RESOLVER",
                    serverId: "Artifactory-1",
                    releaseRepo: "libs-release",
                    snapshotRepo: "libs-snapshot"
                )
              }
             }
                 stage('Building the code'){
                 steps{
                 echo "build is in process"
                 sh 'mvn clean package'
               }
                       
          }
               }
                       
          }
       }


}
