pipeline {
    agent {
        docker {
            image 'public.ecr.aws/docker/library/maven:latest'
            args '-e HOME=/tmp'
        }
    }

    parameters {
        string(name: 'FATHER', defaultValue: 'Vader', description: 'Name of the father')
        string(name: 'PHRASE', defaultValue: 'I am your father!', description: 'Favorite phrase')
    }

    stages {
        stage('Source') {
            steps {
                sh 'mvn --version'
                sh 'git --version'
                git branch: 'main',
                    url: 'https://github.com/ERay620/Ch04-04_03-docker-agent.git'
            }
        }
        stage('Clean') {
            steps {
                sh 'mvn clean'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package -DskipTests'
            }
        }
    }
}
