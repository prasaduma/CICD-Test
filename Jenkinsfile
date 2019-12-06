def tomcatDeployDir = "/opt/tomcat/apache-tomcat-8.5.49/webapps/"
def srcwarPath="/target/project.war"
def dstwarPath= "project.war"

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
        stage('remove old version') {
            steps {
                sh "rm $tomcatDeployDir$dstwarPath"
            }
        }
        stage('Run/Deploy') {
            steps {
                sh "cp $workspace$srcwarPath $tomcatDeployDir"
                echo "http://ec2-35-174-168-193.compute-1.amazonaws.com:8888/project/"
            }
        }
    }
}
