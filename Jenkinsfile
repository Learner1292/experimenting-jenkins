pipeline {
    agent any

    environment {
        JAVA_HOME = '/usr/lib/jvm/java-17-amazon-corretto'
        MAVEN_HOME = '/opt/maven'
        DEPLOY_ENV = 'dev'
    }

    stages {
        stage('Clone') {
            steps {
                git credentialsId: 'github-pat', url: 'https://github.com/your-username/hello-jenkins.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building in ${DEPLOY_ENV} environment"
                sh "${MAVEN_HOME}/bin/mvn clean package"
            }
        }

        stage('Test') {
            steps {
                sh "${MAVEN_HOME}/bin/mvn test"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploy step placeholder"
            }
        }
    }
}

