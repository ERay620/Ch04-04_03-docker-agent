pipeline {
    agent {
        docker { image 'public.ecr.aws/docker/library/maven:latest' }
    }

    parameters {
        string(name: 'FATHER', defaultValue: 'Vader', description: 'Name of the father')
        string(name: 'PHRASE', defaultValue: 'I am your father!', description: 'Favorite phrase')
    }

    stages {
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
