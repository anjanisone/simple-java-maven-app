pipeline {
    agent { node { label 'linux'} }
    options {
        timestamps()
        disableConcurrentBuilds()
    }
    parameters {
        booleanParam(description: 'Skip Tests', name: 'skipTests', defaultValue: false)
        booleanParam(description: 'Nexus IQ', name: 'NEXUS_IQ_SCAN', defaultValue: false)
        booleanParam(description: 'SonarQube', name: 'SONARQUBE_SCAN', defaultValue: false)
    }
    environment {
        JAVA_TOOL_NAME = 'Zulu JDK 8'
        MAVEN_TOOL_NAME = 'Maven 3'
        JAVA_HOME = tool('Zulu JDK 8')
        IS_BUILD_SERVER = "true"
        MAVEN_HOME = tool('Maven 3')
    }
    stages {
        stage('Initialize') {
            steps {
                script {
                   sh 'mvn clean install deploy -DskipTests'
                }
            }
        }
    }
}
