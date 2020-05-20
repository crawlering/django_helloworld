pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                echo 'Hello World,`pwd`'
                sh 'pwd'
                sh 'printenv'
                #sh 'setsid python3.6 manage.py runserver 0.0.0.0:60001 >> /tmp/django.log 2>&1 &'
                script {
		    setsid python3.6 manage.py runserver 0.0.0.0:60001 >> /tmp/django.log 2>&1 &
		    MY_A='123'
                 
}
            }
	        echo '=======$MY_A'
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
}
