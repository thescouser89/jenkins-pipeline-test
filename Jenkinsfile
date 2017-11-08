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
                script {
                    waitUntil {
                        try {
                            sh'''
                                date
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
