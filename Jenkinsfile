pipeline {
    agent any
    parameters {
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
    stages {
        stage("init") {
            steps {
                script {
                   echo 'init stage...'
                }
            }
        }
        stage("build") {
            steps {
                script {
                    echo 'build stage...'
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
                    echo 'test stage...'
                }
            }
        }
        stage("deploy") {
            steps {
                script {
                    echo 'deploy stage...'
                }
            }
        }
    }

//     node {
//         stage('Stage 1') {
//             // test the false value
//        print 'DEBUG: parameter isFoo = ' + params.image
//        print "DEBUG: parameter isFoo = ${params.image}"
//        sh "echo sh isFoo is ${params.image}"
//        if (params.image == 'test') { print "THIS SHOULD DISPLAY" }
//         }
//     }
}



