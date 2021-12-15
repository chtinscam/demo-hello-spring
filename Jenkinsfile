pipeline {
  agent { label 'Jenkins_Slave'}
  stages {
    stage('Checkout'){
        //agent {label 'Jenkins_Slave'}
            steps{
                git "https://github.com/chtinscam/demo-hello-spring.git"
            }
        }
    stage('Mvn Package'){
        //agent {label 'Jenkins_Slave'}
        steps{
            sh "mvn clean package"
        }
    }
    stage('Build Docker Image'){
        //agent {label 'Jenkins_Slave'}
        steps{
            sh 'sudo podman build -t cam/spring-hello .'
        }
    }
    stage('Push Docker Image'){
        //agent {label 'Jenkins_Slave'}
            steps{  
                withCredentials([string(credentialsId: 'pwd_dockerHub1', variable: 'pwd_dockerHub1')]) {
    // some block
                    sh 'sudo podman login docker.io -u 18521496 -p ${pwd_dockerHub1}'
}
                
                sh 'sudo podman tag localhost/cam/spring-hello:latest docker.io/18521496/spring-hello:latest'
                sh 'sudo podman push docker.io/18521496/spring-hello:latest'
            }
    }
    stage('Run'){
        //agent {label 'Jenkins_Slave'}
            steps{
                sh "sudo podman images"
                sh "sudo podman run -dp 9000:8081 docker.io/18521496/spring-hello:latest"
            }
        }
    }
}