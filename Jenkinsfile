pipeline {
    agent {
        docker {
            image 'maven:3.8.7-eclipse-temurin-11' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stages {
        stage('BuildNew') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}
