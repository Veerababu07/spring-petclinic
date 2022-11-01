pipeline {
    agent { lable 'openjdk-11-mvn' }
     triggers { pollSCM('* * * * *') }
     parameters { choice(name: 'BRANCH_TO_BUILD', choices: ['rel_1.0'], description: 'BRANCH TO BUIL IN THE SCRIPT') }
     parameters { choice(name: 'MAVEN BUILD', choices: ['mvn package'], description: 'MAVEN package TO BUIL IN THE SCRIPT') }
     stages ('vcs') {
        stage {
            steps {
               git url :'https://github.com/Veerababu07/spring-petclinic.git',
                 branch : "${params.BRANCH_TO_BUILD}"
            }
        } 
        stage ('build') {
            steps {
               sh "${params.MAVEN BUILD}"
            } 
        }
        stage ('artifacts') {
            steps {
                archiveArtifacts artifacts:'**/target/*.jar'
            }
        }
        stage ('artifacts results') {
            steps {
                junit '**/surefire-reports/*.xml'
            }
        }
    }
    post {
        always {
            echo "buil completed"
        }
    }
}