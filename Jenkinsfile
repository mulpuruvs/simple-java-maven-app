pipeline {
  agent any
  
  tools {
    maven 'maven3'
    jdk 'java8'
  }
  
  stages {
    stage('Build') {
      steps {
        sh "mvn -B -DskipTests clean package"
      }
    }
    
   /* stage('SonarQube Code Analysis') {
            steps {
                //sh "mvn sonar:sonar -Dsonar.host.url=http://54.190.168.185:30002"
                sh "mvn sonar:sonar -Dsonar.host.url=http://54.190.168.185:30025"
              }
        }
    */
    
   /*stage('Test') {
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
      // sh 'scp -r target centos@52.26.244.188:/root/'
      sh 'scp -o StrictHostKeyChecking=no -i /tmp/poc.pem target/my-app-1.0-SNAPSHOT.jar centos@52.26.244.188:/tmp/'
      sh 'ssh -i /tmp/poc.pem centos@52.26.244.188 java -jar /tmp/my-app-1.0-SNAPSHOT.jar'
      // FYR sh './jenkins/scripts/deliver.sh
       // sh 'java -jar 52.26.244.188/root/target/my-app-1.0-SNAPSHOT.jar'
    }
   } */
   
  }
}
