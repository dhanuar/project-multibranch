pipeline{
    agent any
    stages{
        stage("git checkout"){
            when {
                branch "develop"
            }
            steps{
               git credentialsId: 'multibranchpipeline', url: 'https://github.com/dhanuar/project-multibranch'
            }
        }
        stage("maven build"){
            when {
                branch "qa"
            }
            steps{
               sh "mvn package"
            }
        }
    }
}
            
            
         
