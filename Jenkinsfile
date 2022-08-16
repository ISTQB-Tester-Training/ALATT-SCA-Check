pipeline {
    agent any

    stages {
        stage('Build') {
            steps {

                git 'https://github.com/ISTQB-Tester-Training/ALATT-SCA-Check.git'

                sh "mvn compile"
            }
        }
        stage('Unit Test') {
            steps {

               sh"mvn test"
            }
        }
        stage('Code Analysis') {
            steps {

                sh "mvn sonar:sonar -Dsonar.host.url=http://80.158.7.52:30002 -Dsonar.login=credentials('Token-für-Zugriff-auf-SonarQube')"
            }
        }
    }
}