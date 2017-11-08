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
                waitUntil {
                    sh'''
                        echo "hello world"
                        '''
                }
            }
        }
    }
}
