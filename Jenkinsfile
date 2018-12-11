pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /Users/SO-LPT-028/.m2:/root/.m2'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}
