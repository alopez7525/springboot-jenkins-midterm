pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
         }
 
         stage('Build') {
             steps {
                 sh 'chmod +x mvnw'
                 sh './mvnw clean package -DskipTests'
             }
         }

         stage('Archive Artifact') {
             steps {
                 archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
             }
         }
     }
}
