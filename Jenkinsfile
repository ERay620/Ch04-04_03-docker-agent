pipeline {
    agent {
        docker { image 'public.ecr.aws/docker/library/maven:latest' }
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
                dir("${env.WORKSPACE}"){
                    sh 'mvn clean'
                }
            }
        }
        stage('Example1') {
            steps {
                echo "I am your father. My name is ${params.FATHER}"
            }
        }
        stage('Example2') {
            steps {
                echo "I am your father. My name is ${params.FATHER}"
                echo "My favorite phrase is ${params.PHRASE}"
            }
        }
    }
}
