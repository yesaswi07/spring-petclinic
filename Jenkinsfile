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
        sh '''mvn clean verify sonar:sonar \\
  -Dsonar.projectKey=spring-petclinic \\
  -Dsonar.projectName=\'spring-petclinic\' \\
  -Dsonar.host.url=http://65.0.125.61:9000 \\
  -Dsonar.token=sqp_46aea71abd17884e8c85764a860decbdcd9ceb31'''
        sh '''mvn clean verify sonar:sonar \\
  -Dsonar.projectKey=spring-petclinic \\
  -Dsonar.projectName=\'spring-petclinic\' \\
  -Dsonar.host.url=http://65.0.125.61:9000 \\
  -Dsonar.token=sqp_46aea71abd17884e8c85764a860decbdcd9ceb31'''
      }
    }

  }
}