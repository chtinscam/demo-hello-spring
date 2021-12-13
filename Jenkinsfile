pipeline{
   agent none
   stages {
   stage('SCM Checkout'){
       git 'https://github.com/chtinscam/demo-hello-spring.git'
   }
//   stage('Mvn Package'){
//      sh "mvn clean package"
//   }
//   stage('Build Docker Image'){
//      sh 'sudo podman build -t cam/spring-hello .'
//   }
//   stage('Push Docker Image'){
//      sh 'sudo podman login docker.io -u 18521496 -p Tcam12345'
//      sh 'sudo podman tag localhost/cam/spring-hello:latest docker.io/18521496/spring-hello:latest'
//      sh 'sudo podman push docker.io/18521496/spring-hello:latest'
//   }
    stage('Run'){
        sh 'sudo podman images'
       sh 'sudo podman run -dp 9000:8081 docker.io/18521496/spring-hello:latest'
    }
   }
}