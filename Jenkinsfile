pipeline {
    agent any
    tools {nodejs "node16" }
    environment {
        NODE_ENV='production'
    }
    
  
    stages {
        stage('source') {
            steps {
               git 'https://github.com/sd031/aws_codebuild_codedeploy_nodeJs_demo.git'
               sh 'cat index.js'
            }
            
        }
        
         stage('build') {
             environment{
                 NODE_ENV='StagingGitTest'
             }
             
            
            steps {
             echo NODE_ENV
             withCredentials([string(credentialsId: 'a9ca1c19-800f-42d0-acba-d92a510ebe03', variable: 'jagadeesh')]) {
                     // some block
             echo jagadeesh         
            }
                         sh 'npm install'
            }
            
        }
        
         stage('saveArtifact') {
            steps {
              archiveArtifacts artifacts: '**', followSymlinks: false
            }
            
        }
        
        
        
    }
}
