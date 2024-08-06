pipeline{
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage('checkout the code'){
            steps{
                git url:'https://github.com/vijay111083/springboot-maven-course-micro-svc.git', branch: 'master'
            }
        }
        stage('build the code'){
            steps{
                sh 'mvn clean package'
            }
        }
      stage('Docker Build') {
       agent any
       steps {
        sh 'docker build -t vijay11083/spring-petclinic:latest .'
      }
    }
       stage('Docker Push') {
      agent any
      steps {
        withCredentials([usernamePassword(credentialsId: 'vijay11083', passwordVariable: 'Vijay@111083', usernameVariable: 'dockerHubUser')]) {
          sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
          sh 'docker push vijay11083/spring-petclinic:latest'
        }
      }


}
}
}

