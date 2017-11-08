#!/usr/bin/env groovy
pipeline {
    agent {
        node {
            label 'rh-sso-pipeline'
        }
    }
    stages {
        try {
            stage('Input parameters') {
                steps {
                    waitUntil {
                        sh'''
                            echo "hello world"
                            '''
                    }
                }
            }
        } catch(error) {
            sh'''
                echo "woooo"
                '''
        }
    }
}
