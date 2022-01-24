pipeline{
    agent any
    stages{
        stage("git checkout"){
            when {
                expression{
                    env.BRANCH_NAME.equals("develop") ||
                    env.BRANCH_NAME.startsWith("master")
                }
            }
            steps{
               git credentialsId: 'multibranchpipeline', url: 'https://github.com/dhanuar/project-multibranch'
            }
        }
        stage("maven build"){
            when {
                expression{
                    env.BRANCH_NAME.equals("develop") ||
                    env.BRANCH_NAME.startsWith("master")
                }
            }
            steps{
               sh "mvn package"
            }
        }
    }
}
            
            
         
