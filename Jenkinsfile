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
<<<<<<< HEAD
=======
        stage ('Archive the artifacts') {
            steps {
               archiveartifacts artifacts : '**/target/*.jar'
            }
        }
        stage ('junits') {
            steps {
               junit testresults : 'target/surefire-reports/*.xml'
            }
        }
>>>>>>> 04a8f8e99a55f9edc7092f89e0125d6a5df10912

    }
    
}