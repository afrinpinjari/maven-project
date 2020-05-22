pipeline {
    agent any


    stages {
        stage('SCM Checkout'){
          git 'https://github.com/afrinpinjari/maven-project.git'
        }
  }
    {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn test'
                }
            }
        }


        stage ('install Stage') {
            steps {
                withMaven(maven : 'LocalMaven') {
                    sh 'mvn install'
                }
            }
        }
        stage ('deploy-to-tomcat') {
               steps {
                   sshagent(['d2ff33f6-85c6-4295-9d4a-a9d496049696']) {
                        sh 'ssh -o StrictHostKeyChecking=no */target/*.war ec2-user@172.31.22.39:/var/lib/tomcat/webapps'
}
        
    }
}
               }}
