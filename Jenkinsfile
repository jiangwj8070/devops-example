pipeline {
    agent any

    stages {
        stage('Checkout From Git') {
            steps {
                checkout scmGit(branches: [[name: '${tag}']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/jiangwj8070/devops-example.git']])
            }
        }
        stages {
                stage('Build By Maven') {
                    steps {
                        sh '''mvn clean package -Dmaven.test.skip
                        mkdir docker/java
                        mv target/devops-example.jar docker/java/
                        mvn clean'''
                    }
                }
    }
}
