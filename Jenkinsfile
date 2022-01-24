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
                expression{
                    env.BRANCH_NAME.equals("develop") ||
                    env.BRANCH_NAME.startsWith("qa")
                }
            }
            steps{
               sh "mvn package"
            }
        }
    }
}
            
            
         
