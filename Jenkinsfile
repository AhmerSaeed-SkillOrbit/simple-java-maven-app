pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /Users/SO-LPT-028/.m2:/root/.m2'
        }
    }
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
                sh 'mvn clean install'
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}