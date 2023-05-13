pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/giansantoro/inf335-jenkins'
            }
        }
        
        stage('Maven Build') {
            steps {
                script {
                    def mavenHome = tool 'M3'
                    sh "${mavenHome}/bin/mvn -B -DskipTests clean package"
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    def mavenHome = tool 'M3'
                    sh "${mavenHome}/bin/mvn test"
                }
            }
        }
    }
}
