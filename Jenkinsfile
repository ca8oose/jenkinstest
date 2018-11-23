pipeline {
         agent any
         stages {
                 stage('One') {
                 steps {
                     echo 'Hi, this is Jeffery Bradley from SE2 TOOLS'
                 }
                 }
                 stage('Two') {
                 steps {
                    input('Do you want to proceed?')
                 }
                 }
                 stage('Three') {
                 when {
                       not {
                            branch "master"
                       }
                 }
                 steps {
                       echo "Hello, How can I help you"
                 }
                 }
                 stage('Four') {
                 parallel { 
                            stage('Unit Test') {
                           steps {
                                echo "Running the unit test...This hopefully works"
                           }
                           }
                            stage('Integration test') {
                              agent {
                                    docker {
                                            reuseNode true
                                            image 'ubuntu'
                                           }
                                    }
                              steps {
                                echo "Running the integration test...If this works Ill be happy"
                              }
                           }
                           }
                           }
              }
}
