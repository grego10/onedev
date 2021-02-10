pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
        }
        steps {
            sh 'apk update && apk upgrade && \ apk add git'
        }
    }
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
    }
}