pipeline {
    agent any
    stages {
        stage("检查更新") {
	    when {
	        expression { "${env.GIT_COMMIT}"!="${env.GIT_PREVIOUS_COMMIT}" }
	    }
	    steps {
	        echo "GIT_COMMIT: ${env.GIT_COMMIT} \n GIT_PREVIOUS_COMMIT: ${env.GIT_PREVIOUS_COMMIT}"
	        echo "对比版本"
	        echo "版本发生变化,执行更新"
		script {
		    println "查看是否程序正在运行..."
                    sh 'PY_PID=`ps -aux | grep \'/bin/python3.6 manage.py runserver 0.0.0.0:60001\' | grep -v grep | awk \'NR==1{print $2}\'`'
                    echo '${env.PY_PID}'
                    sh 'kill -9 $PY_PID'
                    echo "hello"
		}
	    }	
    }
    }
}

