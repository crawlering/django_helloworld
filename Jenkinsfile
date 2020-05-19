pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                echo 'Hello World,`pwd`'
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
}
