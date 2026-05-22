pipeline {
 agent any
 stages {
  stage('Git') {
   steps {git 'https://github.com/Dmitry-Anastasiev/Homework-8.2.git'}
  }
  stage('Test') {
   steps {
    sh 'go test .'
   }
  }
  stage('Build') {
   steps {
    sh 'docker build . -t 127.0.0.1:8082/hello-world:v$BUILD_NUMBER'
   }
  }
  stage('Push') {
   steps {
    sh 'docker login 127.0.0.1:8082 -u admin -p admin && docker push 127.0.0.1:8082/hello-world:v$BUILD_NUMBER && docker logout'   }
  }
 }
}