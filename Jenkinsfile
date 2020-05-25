pipeline {
    stages {
        stage("检查更新")
	    echo "GIT_COMMIT: $GIT_COMMIT \n GIT_PREVIOUS_COMMIT: $GIT_PREVIOUS_COMMIT"
	    echo "对比版本"
	    when {
	        expression { $GIT_COMMIT==$GIT_PREVIOUS_COMMIT }
	    }
	    steps {
	        echo "版本发生变化,执行更新"
		script {
		    println "查看是否程序正在运行..."
		    sh "ps -aux | grep '/bin/python3.6 manage.py runserver 0.0.0.0:60001' | grep -v grep | awk 'NR==1{print $2}'"
                    echo "hello"
		}
	    }	

    }
}

