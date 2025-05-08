pipeline {
     agent {
        docker { image 'public.ecr.aws/docker/library/maven:latest' }
    }

    stages {
        stage('Example1') {
            steps {
                echo "I am your father.  My name is ${params.FATHER}"
            
            }
        }
          stages {
        stage('Example2') {
            steps {
                echo "I am your father.  My name is ${params.FATHER}"
                echo "My favorite phrase is ${params.PHRASE}"
            }
        }
    }
}
