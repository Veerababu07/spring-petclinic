pipeline{
    agent (label 'jdk11')
    triggers {  ('* * * * *')
    }
    stages {
        stage ('vcs') {
            steps {
                git url: 'https://github.com/Veerababu07/spring-petclinic.git',
                    gitbranch : 'main'
            }    
        }
        stage {
            steps ('build') {
                sh 'mvn package'
            }
        }
    }
}