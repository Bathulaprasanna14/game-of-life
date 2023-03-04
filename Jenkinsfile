pipeline{
    agent { label 'UBUNTU_JDK'
    }
    stages{
        stage('vcs'){
            steps{
                git url: 'https://github.com/Bathulaprasanna14/game-of-life.git',
                      branch: 'master'
            }
        }        
        stage('package'){
           steps {
             sh 'mvn package'
           }
        }
        stage('post build'){
            archiveArtifacts artifacts: '**//target/gameoflife.war',
                 onlyIfSuccessful : true
            JunittestResults : '**//surefire-reports/TEST-com*.xml'
        }
    }
}