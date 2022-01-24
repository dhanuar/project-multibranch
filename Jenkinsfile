pipeline{
    agent any
    triggers {
      pollSCM '* * * * *'
    }
    stages{
        stage("git checkout"){
            when {
                branch "develop"
            }
            steps{
               git credentialsId: 'multibranchpipeline', url: 'https://github.com/dhanuar/project-multibranch'
            }
            stage("maven build"){
            when {
                branch "develop"
            }
            steps{
               sh "mvn package"
            }
        }
    }  
}
}
