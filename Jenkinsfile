pipeline {
    agent any
    stages {
        stage ('build') {
            steps {
                withMaven(
                        // Maven installation declared in the Jenkins "Global Tool Configuration"
                        maven: 'M3',
                    ) {

                      // Run the maven build
                      sh "mvn clean install"

                    }
                stash 'target/*.jar'
            }
        }
        stage ('analyze') {
            steps {
                sh 'sleep 5'
            }
        }
        stage ('acceptance-test') {
            steps {
                sh 'sleep 5'
            }
        }
        stage ('stage') {
            steps {
                unstash
                sh 'ls -l target'
                sh 'sleep 5'
            }
        }
        stage ('ask') {
            steps {
                sh 'sleep 5'
            }
        }
        stage ('deploy') {
            steps {
                unstash
                sh 'ls -l target'
                sh 'sleep 5'
            }
        }
    }
}
