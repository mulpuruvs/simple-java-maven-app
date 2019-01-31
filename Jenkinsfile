pipeline {
  agent any
  
  tools {
    maven 'Maven'
    jdk 'java1.8.0'
  }
  
  stages {
    stage('Build') {
      steps {
        sh "mvn -B -DskipTests clean"
      }
    }
  }
}
