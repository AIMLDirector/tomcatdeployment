#!/usr/bin/env groovy

pipeline {

    agent {
        docker {
            image 'centos'
            args '-u root'
            args '-p 8000:8080'
        }
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'yum  install -y tomcat '
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'systemctl enable tomcat; /usr/local/tomcat/bin/catalina.sh run'
                sh 'curl http://localhost:8080'
            }
        }
    }
}
