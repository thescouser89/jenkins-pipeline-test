#!/usr/bin/env groovy
def retry_script(String label, Closure body) {
    script {
        waitUntil {
            try {
                body.call()
                true
            } catch(error) {
                emailext (
                    subject: "Stage " + label + " failed!",
                    body: "See: ${env.BUILD_URL}",
                    recipientProviders: [[$class: 'DevelopersRecipientProvider'],
                                         [$class: 'RequesterRecipientProvider']],
                    to: 'dcheung@redhat.com,hukhan@redhat.com'
                )
                input "Try to re-run the stage?"
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

