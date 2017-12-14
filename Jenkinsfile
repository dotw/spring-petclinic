pipeline {
  agent {docker 'maven:3.5-alpine'}
  stages {
    stage 'check cout' {
      steps {
        git 'https://github.com/dotw/spring-petclinic.git'
      }
    }

    stage 'build' {
      steps {
        sh 'mvn clean package'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
  }
}
