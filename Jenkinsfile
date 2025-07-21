pipeline {
    agent any
    
    tools{
        jdk 'jdk17'
        maven 'maven3'
    }

    stages {
         stage('Git CHeckout') {
             steps {
                 git branch: 'feature-1', url: 'https://github.com/jaiswaladi246/Petclinic.git'
             }
         }
        
        stage('Compile') {
            steps {
                 sh "mvn clean compile"
            }
        }
         stage('Build') {
            steps {
                 sh "mvn clean package -DskipTests=true"
            }
         }
         
         stage('Deploy') {
            steps {
                 sh "cp target/petclinic.war /opt/apache-tomcat-9.0.65/webapps/petclinic.war"
            }
         }
    }
}
    
