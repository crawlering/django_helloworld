node {
    stage('start...') {
    GIT_COMMIT=sh 'echo $GIT_COMMIT'
    GIT_PREVIOUS_COMMIT=sh 'echo $GIT_PREVIOUS_COMMIT'
    if (GIT_COMMIT==GIT_PREVIOUS_COMMIT) {
        println '代码拉取更新,'
	println '查看是否有执行程序是否正在执行...'
    }
    else {
        println '版本没有变化,不做更新'
    }
    }
}
