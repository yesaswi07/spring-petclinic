pipeline {
  agent any
  stages {
    stage('Compile') {
      steps {
        sh './mvnw clean compile'
      }
    }

    stage('static analysis') {
      steps {
        sh '''./mvnw sonar:sonar \\
  -Dsonar.host.url=http://localhost:9000 \\
  -Dsonar.projectKey=spring-petclinic \\
  -Dsonar.token=sqp_46aea71abd17884e8c85764a860decbdcd9ceb31'''
      }
    }

    stage('Unit Test') {
      steps {
        sh './mvnw "-Dtest=**/petclinic/*/*.java" test'
        junit '**/target/surefire-reports'
      }
    }

  }
}