def gv
def versions = ['1.1.0', '1.2.0', '1.3.0',  '1.4.0',  '1.5.0']

pipeline {
    agent any
    parameters {
        choice(name: 'VERSION', choices: versions , description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
    stages {
        stage("init") {
            steps {
                script {
                   gv = load "script.groovy"
                }
            }
        }
        stage("build") {
            steps {
                script {
                    gv.buildApp()
                }
            }
        }
        stage("test") {
            when {
                expression {
                    params.executeTests
                }
            }
            steps {
                script {
                    gv.testApp()
                }
            }
        }
        stage("deploy") {
            steps {
                script {
                    gv.deployApp()
                    println("VERSION = ${params.choices}")
                }
            }
        }
    }
}
