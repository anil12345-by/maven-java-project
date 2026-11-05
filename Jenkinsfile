
pipeline {
    agent any

    tools {
        maven 'MAVEN HOME'
    }

    stages {

        stage('git repo & clean') {
            steps {
                bat 'if exist maven-java-project rmdir /s /q maven-java-project'
                bat 'git clone https://github.com/anil12345-by/maven-java-project.git'
                bat 'mvn clean -f maven-java-project/pom.xml'
            }
        }

        stage('install') {
            steps {
                bat 'mvn install -f maven-java-project/pom.xml'
            }
        }

        stage('test') {
            steps {
                bat 'mvn test -f maven-java-project/pom.xml'
            }
        }

        stage('package') {
            steps {
                bat 'mvn package -f maven-java-project/pom.xml'
            }
        }
    }
}
