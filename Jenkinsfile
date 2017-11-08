#!/usr/bin/env groovy
pipeline {
    agent {
        node {
            label 'rh-sso-pipeline'
        }
    }
    stages {
        stage('Input parameters') {
            steps {
                sh'''
                echo "hello world"
                '''
            }
        }
    }
}
