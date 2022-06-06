pipeline {
    agent any
    stages {
        stage('Build Application') {
            steps {
                echo "Build Application"
                script {
                    sh 'mvn clean install'
                    sh 'mvn --version'
                }
            }
            post {
                success {
                    echo "Now Archiving the Artifacts...."
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }
        stage('Deploy in Staging Environment'){
            steps{
               build job: 'Deploy_Application_Staging_Env'
 
            }
            
        }
        stage('Deploy to Production'){
            steps{
                timeout(time:5, unit:'DAYS'){
                    input message:'Approve PRODUCTION Deployment?'
                }
                build job: 'Deploy_Application_Prod_Env'
            }
        }
    }
}
            
