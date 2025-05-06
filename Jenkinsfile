pipeline {
    agent {
        docker { image 'public.ecr.aws/docker/library/maven:3.9-sapmachine' }
    }
    stages {
        stage('Source') {
            steps {
                sh 'mvn --version'
                sh 'git --version'
                git branch: 'main',
                    url: 'https://github.com/LinkedInLearning/essential-jenkins-2468076.git'
            }
        }
      stage('Clean') {
            steps {
                dir("${env.WORKSPACE}"){
                    sh 'mvn clean'
                }
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
