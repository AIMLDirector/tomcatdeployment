#!/usr/bin/env groovy

pipeline {

    agent {
        docker {
            image 'centos'
            args '-u root'
        }
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'yum  install-y tomcat '
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'systemctl enable tomcat; systemctl start tomcat'
            }
        }
    }
}
