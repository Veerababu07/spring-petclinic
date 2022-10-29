pipeline {
     agent any
    triggers { ('* * * * *') }
    stages ('vcs') {
        stage {
            git url : 'https://github.com/Veerababu07/spring-petclinic.git',
             branch : 'main'
        }
        stage ('build') {
            step {
               sh 'mvn package'
            }
        }
        stage ('artifacts') {
            step {
                archiveArtifacts artifacts  '**/target/*.jar'
            }
        }
        stage ('artifacts results') {
            step {
                junit '**/surefire-reports/*.xml'
            }
        }
    }
}
