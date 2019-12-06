def tomcatDeployDir = "/opt/tomcat/apache-tomcat-8.5.49/webapps/"
def srcwarPath="/target/project.war"
def dstwarPath= ""

pipeline {

    
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
                sh "echo $tomcatDeployDir"
                sh "sudo cp $workspace$srcwarPath $tomcatDeployDir"
            }
        }
    }
}
