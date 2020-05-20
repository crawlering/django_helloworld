pipeline {
    agent any
    stages {
    stage('pull code'){
        steps {
        echo 'pull code success!'
    }}
    }

    post {
        always {
	    sh 'JENKINS_NODE_COOKIE=dontKillMe setsid python3.6 manage.py runserver 0.0.0.0:60001 >> /tmp/django.log 2>&1 &'
	}
    }
}
