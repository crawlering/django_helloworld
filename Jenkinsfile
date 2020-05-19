pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                echo 'Hello World,`pwd`'
                sh 'pwd'
                sh 'python3.6 manage.py runserver 0.0.0.0:60001&'
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
}
