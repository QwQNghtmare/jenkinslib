#!groovy

@Library('jenkinslib') _
def tools = new org.devops.tool()

pipeline {
    agent any
    options {
        timeout(time: 1, unit: 'HOURS')
    }
    parameters {
        string (name: 'test', defaultValue: 'abcd', description: '')
    }
    stages {
        stage('clone code') {
            when {
                environment name: 'test', value: 'abcd'
            }
            steps {
                input id: 'Go', message: 'do we continue?', ok: 'yes,continue', parameters: [choice(choices: ['yes', 'no'], description: '', name: 'test')], submitter: 'admin'
                echo 'hello'
                tools.PrintMs('abc')
            }
        }
    }
}
