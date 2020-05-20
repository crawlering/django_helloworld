pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                echo 'Hello World,`pwd`'
                sh 'pwd'
                sh 'printenv'
                script {
		    setsid python3.6 manage.py runserver 0.0.0.0:60001 >> /tmp/django.log 2>&1 &
		    MY_A='123'
                 
}
            }
	        echo '=======$MY_A'
                echo 'GIT_PREVIOUS_COMMIT: $GIT_PREVIOUS_COMMIT , GIT_COMMIT: $GIT_COMMIT'
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
}
