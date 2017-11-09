#!/usr/bin/env groovy
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

pipeline {
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

