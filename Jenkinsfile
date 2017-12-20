pipeline {
    agent { docker 'maven:3.5-alpine'}
    stages {
        stage('check out') {
            steps {
                git 'https://github.com/dotw/spring-petclinic.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean package'
                junit '**/target/surefire-reports/TEST-*.xml'
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
        stage('deploy') {
            steps {
                input 'Do you approve the deployment?'
                echo 'Deploying....'
            }
        }
    }
}
