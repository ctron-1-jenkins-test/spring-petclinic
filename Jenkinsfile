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
                stash name:"result", includes:"target/*.jar"
            }
        }
        stage ('analyze') {
            steps { 
                withSonarQubeEnv('sonar') {
      sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.2:sonar'
    }
            }
        }
        stage ('acceptance-test') {
            steps {
                sh 'sleep 5'
            }
        }
        stage ('stage') {
            steps {
                unstash "result"
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
                unstash "result"
                sh 'ls -l target'
                sh 'sleep 5'
            }
        }
    }
}
