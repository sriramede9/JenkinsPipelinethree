pipeline {
    agent any
    stages {
        stage('---clean---') {
            steps {
                bat "rmdir /s /q JenkinsPipelinethree "
                bat "git clone https://github.com/sriramede9/JenkinsPipelinethree.git"
               // bat "cd JenkinsPipelinethree"
                bat "mvn clean "
            }
        }
        stage('--test--') {
            steps {
                bat "mvn test "
            }
        }
        stage('--package--') {
            steps {
                bat "mvn package "
            }
        }
    }
}