  
     pipeline{
    agent any 
    tools{
         maven 'M2_HOME'
    }
    stages{
    stage('maven clean'){
        steps{
        sh  'mvn clean'
        }
    }
    stage('maven install'){
        steps{
          sh  'mvn install'
            
        }
    }
    stage('maven package'){
        steps{
         sh   'mvn package'
        }
    }
   stage('upload artifact'){
        steps{
           nexusArtifactUploader artifacts: [[artifactId: 'bioMedical', 
           classifier: '', file: 'target/biomedical-0.0.1-SNAPSHOT.jar', 
           type: 'jar']], credentialsId: 'NexusID', groupId: 'QA', 
           nexusUrl: '98.58.119.40:8081/repository/Manuella-repo/', 
           nexusVersion: 'nexus3', protocol: 'http', repository: 'manuella-repo', version: 'V1'
        }
    }

    }

}