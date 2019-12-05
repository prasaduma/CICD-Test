pipeline {
    agent any
    
    stages {
        stage('SCM') {
            steps{
             git url: 'https://github.com/prasaduma/CICD-Test.git'
            }
    
        }
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') { 
            steps {
                sh 'mvn test' 
            }
        }
        stage('Run/Deploy') {
            steps {
                 sh ' mvn -Djetty.port=8888 jetty:run'
            }
        }
    }
}