pipeline {
     agent any
    triggers { ('*/10 * * * *') }
    stages ('vcs') {
        stage {
            steps {
               git url : 'https://github.com/Veerababu07/spring-petclinic.git',
                 branch : 'main'
            }
        }
        stage ('build') {
            steps {
               sh 'mvn package'
            }
        }
        stage ('artifacts') {
            steps {
                archiveArtifacts artifacts  '**/target/*.jar'
            }
        }
        stage ('artifacts results') {
            steps {
                junit '**/surefire-reports/*.xml'
            }
        }
    }
}
