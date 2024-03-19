pipeline {
    agent any 
        tools {
               maven "maven-linux"
               jdk "java-linux"
              }
    stages {
        stage ('checkout') {
            steps{
                git clone "https://github.com/sainathkasturi/SparkJavaWarProject.git"
            }
        }
        stage ('build') {
            steps {
                  sh 'mvn clean package'
            }
        }
        stage ('deploy') {
            steps {
                   sh 'opt/deploy.sh'
            }
        }
        stage ('artifact') {
            steps {
                archiveArtifacts 'target/*.war'
            }
        }
    }
}
        
