pipeline {
    agent any
    stages {
          stage('Build Application') {
            steps { 
                script{
                 sh 'mvn clean install'
                }
         }
          }
    
//             post {
//                 success {
//                     echo "Now Archiving the Artifacts...."
//                     archiveArtifacts artifacts: '**/*.war'
//                 }
//             }
//         }
//         stage('Deploy in Staging Environment'){
//             steps{
//                build job: 'Deploy_Application_Staging_Env'
 
//             }
            
//         }
        stage('Deploy to Production'){
            steps{
                echo "Helloworld"
        }
       }
    }
}
            
