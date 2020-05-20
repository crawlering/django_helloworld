node {
    stage('start...') {
    sh 'printenv'
    GIT_COMMIT=sh returnStdout: true ,script: 'echo $GIT_COMMIT'
    GIT_PREVIOUS_COMMIT=sh returnStdout: true ,script: 'echo $GIT_PREVIOUS_COMMIT'
    echo GIT_COMMIT
    sh 'echo $GIT_COMMIT'
    if (GIT_COMMIT==GIT_PREVIOUS_COMMIT) {
        println GIT_COMMIT
        println GIT_PREVIOUS_COMMIT
        println '代码拉取更新,'
	println '查看是否有执行程序是否正在执行...'
    }
    else {
        println '版本没有变化,不做更新'
    }
    }
}
