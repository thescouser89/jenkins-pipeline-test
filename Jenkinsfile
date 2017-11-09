#!/usr/bin/env groovy
pipeline {
    def retry_script(String label, Closure body) {
        script {
            waitUntil {
                try {
                    body.call()
                        true
                } catch(error) {
                    input "Retry the job?"
                        false
                }
            }
        }
    }
    agent {
        node {
            label 'rh-sso-pipeline'
        }
    }
    stages {
        stage('Input parameters') {
            steps {
                retry_script("test") {
                    sh'''
                        date
                        echo "hello world
                        '''
                }
            }
        }
    }
}
