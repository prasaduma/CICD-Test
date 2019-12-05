pipeline {
    agent any
    
    stages {
        stage('SCM') {
            steps{
             scm
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