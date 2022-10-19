pipeline{
    agent { label 'jdk11' }
    stages {
        stage ('vcs') {
            steps {
                git url: 'https://github.com/Veerababu07/spring-petclinic.git',
                    branch : 'main'
            }    
        }
        stage {
            steps ('build') {
                sh 'mvn package'
            }
        }
    }
}