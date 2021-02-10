pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
        }
        seteps {
            sh 'apk update && apk upgrade && apk add --no-cache bash git openssh'
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