#!/usr/bin/env groovy

pipeline {

    agent {
      
        docker {
            image 'centos'
            args '-u root'
            args '-p 8888:8080'
        }
    }

    stages {
        stage('Build') {
            steps {
                checkout scm
                echo 'Building...'
                sh 'yum  install -y tomcat '
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'systemctl enable tomcat; /usr/libexec/tomcat/server start &'
                
            }
        }
    }
}
