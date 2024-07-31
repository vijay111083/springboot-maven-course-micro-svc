pipeline{
    agent any
    tools{
        maven 'maven-3.8.4'
    }
    stages{
        stage('checkout the code'){
            steps{
                git url:'https://github.com/bcreddydevops/springboot-maven-course-micro-svc.git', branch: 'master'
            }
        }
        stage('build the code'){
            steps{
                sh 'mvn clean package'
            }
        }
     }
}
