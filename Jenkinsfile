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
                    try {
                        sh'''
                            echo "hello world"
                            '''
                    } catch(error) {
                        sh'''
                        echo "woooo"
                        '''
                    }
                }
            }
        }
    }
}
