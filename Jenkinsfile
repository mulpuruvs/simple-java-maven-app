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
      sh 'scp -r target centos@52.26.244.188:/root/'
      // FYR sh './jenkins/scripts/deliver.sh
       sh 'java -jar 52.26.244.188/root/target/my-app-1.0-SNAPSHOT.jar'
    }
   }
   
  }
}
