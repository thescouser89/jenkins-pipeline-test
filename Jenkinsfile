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
                    script {
                        try {
                            sh'''
                                echo "hello world
                                '''
                            true
                        } catch(error) {
                            input "Retry the job?"
                            false
                        }
                    }
                }
            }
        }
    }
}
