  pipeline {
       agent any

       stages {
           stage('Build') {
               steps {
                   sh 'mvn clean install'
               }
           }
           stage('Docker Build') {
               steps {
                   script {
                       docker.build("my-app:latest")
                   }
               }
           }
           stage('Docker Run') {
               steps {
                   script {
                       docker.image("my-app:latest").run("-p 8080:8080")
                   }
               }
           }
       }
   }
