pipeline{
    agent ( label node1 )
    triggers ('* * * * *')
    stages {
        stage ("vcs") {
            steps {
                git url : 'https://github.com/Veerababu07/spring-petclinic.git'
              branch : 'main'
            }
            
        }
        stage ("build") {
            steps {
                sh "mvn package"
            }
        }

    }
    
}