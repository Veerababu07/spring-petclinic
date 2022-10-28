pipeline{
    agent {label 'jdk11'}
     stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/Veerababu07/spring-petclinic.git',
                    branch : 'main'
            }    
        }
        stage('build') {
            steps  {
                sh 'usr/share/maven/bin/mvn package'
            }
        }
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

    }
}