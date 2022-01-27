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
                branch "develop"
            }
            steps{
               sh "mvn package"
            }
        }
        stage("maven build"){
            when {
                branch "develop"
            }
            steps{
               sh "mvn package"
            }
        }
         stage("sonarqube analyisis"){
            when {
                branch "develop"
            }
            steps{
               withSonarQubeEnv('sonar7') {
               sh "mvn sonar:sonar"
               }
            }
        }
        stage("sonarqube status"){
            when {
                branch "develop"
            }
            steps{
               timeout(time: 1, unit: 'HOURS') {
                //    For this to work, we should add webhook in sonar
                //    http://172.31.3.50:8080/sonarqube-webhook/
                    script{
                        def qg = waitForQualityGate()
                        if (qg.status != 'OK') {
                            error "Pipeline aborted due to quality gate failure: ${qg.status}"
                        }
                 }
        }
    }
}
            
            
         
