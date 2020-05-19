pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                echo 'Hello World,`pwd`'
                sh 'pwd'
                sh 'nohup python3.6 manage.py runserver 0.0.0.0:60001 >> /tmp/django.log 2>&1 &'
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
}
