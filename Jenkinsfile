pipeline {
    agent any
    
    stages {
        stage('One') {
            steps {
                echo 'Hi, this is Zulaikha from edureka'
            }
        }
        
        stage('Two') {
            steps {
                // Your steps for stage Two
            }
            // Prompt for input before proceeding
            input(message: 'Do you want to proceed?')
        }
        
        stage('Three') {
            when {
                // Execute stage Three only if not on the master branch
                not {
                    branch "master"
                }
            }
            steps {
                echo "Hello"
            }
        }
        
        stage('Four') {
            parallel {
                stage('Unit Test') {
                    steps {
                        echo "Running the unit test..."
                    }
                }
                stage('Integration test') {
                    agent {
                        docker {
                            // Define Docker image for integration tests
                            image 'ubuntu'
                            reuseNode false
                        }
                    }
                    steps {
                        echo 'Running the integration test..'
                    }
                }
            }
        }
    }
}

