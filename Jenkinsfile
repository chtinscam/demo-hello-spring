pipeline {

  agent none 

  stages {
      stage('SCM Checkout'){
        agent { node }
        steps{
        sh "git clone https://github.com/chtinscam/demo-hello-spring.git"
        }
      }
//   stage('Mvn Package'){
//      sh "mvn clean package"
//   }
//   stage('Build Docker Image'){
//      sh 'sudo podman build -t cam/spring-hello .'
//   }
//   stage('Push Docker Image'){
//      sh 'sudo podman Login docker.io -u 18521496 -p Tcam12345'
//      sh 'sudo podman tag localhost/cam/spring-hello:latest docker.io/18521496/spring-hello:latest'
//      sh 'sudo podman push docker.io/18521496/spring-hello:latest'
//   }
    // stage('Run'){
    //     agent { node {label 'Built-In Node'}}
    //     steps{
    //     sh "sudo podman images"
    //    sh "sudo podman run -dp 9000:8081 docker.io/18521496/spring-hello:latest"
    //    }
    // }
   }
  }