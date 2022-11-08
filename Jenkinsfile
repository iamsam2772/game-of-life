pipeline {
    agent {label 'game' }
    stages {
        stage ('source code  from git remote repository') {
            steps {
                git branch: "master", url: 'https://github.com/iamsam2772/game-of-life.git'
            }
        }
        stage('To build maven package') {
            steps {
                sh "mvn package"
            }
        }
        stage("archive artifact") {
            steps {
                archiveArtifacts '**/target/*.jar'
            }
        }
        stage("junit Reports") {
            steps {
                junit '**/surefire-reports/*.xml'
            }
        }
    }
}
