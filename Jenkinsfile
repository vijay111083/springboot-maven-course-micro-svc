pipeline{
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage('checkout the code'){
            steps{
                git url: https://github.com/vijay111083/springboot-maven-course-micro-svc.git, branch: 'master'
            }
        }
        stage('build the code'){
            steps{
                sh 'mvn clean package'
            }
        }
}
}
