pipeline {
    parameters {
        choice(name: 'BRANCH_TO_BUILD', choices: ["rel_1.0", "main"], description: 'BRANCH TO BUIL IN THE SCRIPT')
        string(name: 'MAVEN_GOAL', defaultValue: 'package', description: 'MAVEN PACKAGE')
    } 
    stages {
        stage ('vcs') {
            steps {
               git url :'https://github.com/Veerababu07/spring-petclinic.git',
                 branch : "rel_1.0 ${params.BRANCH_TO_BUILD}"
            }
        } 
        stage ('build') {
            steps {
               sh "${params.MAVEN_GOAL}"
            } 
        }
        stage ('artifacts') {
            steps {
                archiveArtifacts artifacts :'**/target/*.jar'
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