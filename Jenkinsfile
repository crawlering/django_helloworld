pipeline {
    agent any
    stages {
        stage("检查更新") {
	    when {
	        expression { "${env.GIT_COMMIT}"=="${env.GIT_PREVIOUS_COMMIT}" }
	    }
	    steps {
	        echo "GIT_COMMIT: ${env.GIT_COMMIT} \n GIT_PREVIOUS_COMMIT: ${env.GIT_PREVIOUS_COMMIT}"
	        echo "对比版本"
	        echo "版本发生变化,执行更新"
		script {
		    println "查看是否程序正在运行..."
                    PY_PID = sh (script: "ps -aux | grep '/bin/python3.6 manage.py runserver 0.0.0.0:60001' | grep -v grep | awk 'NR==1{print \$2}'", returnStdout: true) 
                    sh 'echo $PY_PID'
                    sh 'printenv'
                    println PY_PID
                    if (PY_PID) {
                        println  "查询到进程，杀掉该进程: ${PY_PID}"
                        env.PY_PID = PY_PID
                    
                        sh 'kill -9 ${PY_PID}'
                    }else{
                        echo "未查询到运行的进程，不做任何操作"
                    }

                    
		}
	    }	
          steps {
                    echo "启动服务"
                    sh 'JENKINS_NODE_COOKIE=dontKillMe setsid python3.6 manage.py runserver 0.0.0.0:60001 >> /tmp/django.log 2>&1 &'
                    PY_PID = sh (script: "ps -aux | grep '/bin/python3.6 manage.py runserver 0.0.0.0:60001' | grep -v grep | awk 'NR==1{print \$2}'", returnStdout: true) 
                    println ("服务启动完成，进程号为："+PY_PID)

                }
    }
    }
}

