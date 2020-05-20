node {
    stage('pull code'){
        echo 'pull code success!'
	sh 'setsid python3.6 manage.py runserver 0.0.0.0:60001 >> /tmp/django.log 2>&1 &'
	def MY_X='abc'
	echo ${MY_X}
    }
}
