 pipeline {
  agent any
  
  tools {
    maven 'Maven'
    jdk 'java1.8.0'
  }
  
  stages {
    stage('Build') {
      steps {
        sh "mvn -B -DskipTests clean package"
      }
    }
   stage('Test') {
    steps {
      sh "mvn test"
    }
    post {
     always {
       junit 'target/surefire-reports/*.xml'
     }
    }
   }
   stage('Deploy') {
    steps {
      // FYR sh './jenkins/scripts/deliver.sh
       sh 'java -jar target/sample-app-1.0-SNAPSHOT.jar'
    }
   }
   
  }
}
