pipeline {
    agent any
    environment {
            GIT_COMMIT='''${sh(
            returnStdout: true,
            script: "echo $GIT_COMMIT"
            )}
            '''
            GIT_PREVIOUS_COMMIT='''
            ${sh(
            returnStdout: true,
            script: "echo $GIT_PREVIOUS_COMMIT"
            )
            }
            '''

    }
    stages {
        stage('查看环境') {
            steps {
            sh 'printenv'
            

        }
        }
        stage("检查更新") {
	    when {
	        expression { GIT_COMMIT==GIT_PREVIOUS_COMMIT }
	    }
	    steps {
	        echo "GIT_COMMIT: $GIT_COMMIT \n GIT_PREVIOUS_COMMIT: $GIT_PREVIOUS_COMMIT"
	        echo "对比版本"
	        echo "版本发生变化,执行更新"
		script {
		    println "查看是否程序正在运行..."
                    sh 'ps -aux'
                    echo "hello"
		}
	    }	
    }
    }
}

