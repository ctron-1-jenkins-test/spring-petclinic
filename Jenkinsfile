node ('build') {
    stage('build & test') {
        sh 'sleep 5'
    }
    stage ('analysis') {
        sh 'sleep 5'
    }
}

stage ('acceptance-test') {
    parallel ( 
        chrome: {
            node ('test') {
                sh 'sleep 5'
            }
        },
        firefox: {
            node ('test') {
                sh 'sleep 5'
            }
        },
        edge: {
            node ('test') {
                sh 'sleep 5'
            }
        }
    )
}

node {

    stage ('staging') {
        sh 'sleep 5'
    }
    stage ('manual-approval') {
        input 'Are you sure?'
    }
    stage ('deploy') {
        sh 'sleep 5'
    }
}
