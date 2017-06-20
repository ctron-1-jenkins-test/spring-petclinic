pipeline {
    agent any
    stages {
        stage ('build') {
            steps {
withMaven(
        // Maven installation declared in the Jenkins "Global Tool Configuration"
        maven: 'M3',
        // Maven settings.xml file defined with the Jenkins Config File Provider Plugin
        // Maven settings and global settings can also be defined in Jenkins Global Tools Configuration
        mavenSettingsConfig: 'my-maven-settings',
        mavenLocalRepo: '.repository') {

      // Run the maven build
      sh "mvn clean install"

    }           
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
                sh 'sleep 5'
            }
        }
    }
}
