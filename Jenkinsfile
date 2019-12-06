pipeline {
    def tomcatDeployDir = "/opt/tomcat/"
    def workspace = pwd()
    def warPath ="file.war"
    
    agent any
    
    stages {
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
               
                 sh "echo $workspace"
            }
        }
    }
}
