pipeline {
    agent any

    triggers {
        githubPush()   
    }

    stages {

        stage('Clone') {
            steps {
                git branch: 'develop', url: 'https://github.com/khaoula-errachidi/cargo-tracker-UM6P1'
            }
        }

        stage('Build & Test with Coverage') {
            steps {
               bat 'mvn clean verify'
               //echo ' test'
            }
        }

     
    }
//
    post {
        success {
            echo 'Build et analyse terminés avec succès !'
        }
        failure {
            echo 'Échec du build ou des tests.'
        }
    }
}
