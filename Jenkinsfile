pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-u root:root'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh '''
                    apk update;
                    apk add --no-cache git;
                    apk add --no-cache openssh;
                    git -v;
                '''
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