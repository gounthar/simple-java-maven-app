pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '/opt/maven/bin/mvn -B -DskipTests clean package'git commit -m "Commit message"

            }
        }
        stage('Test') {
            steps {
                sh '/opt/maven/bin/mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}
