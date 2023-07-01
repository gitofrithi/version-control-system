pipeline {
    agent any
            stages {
                stage('one'){
                    steps {
                        echo 'Hi, This is Ritheesh Padavala the future'
                    }
                }    
                stage('two'){
                    steps {
                        input('do you want to proceed')
                    }    
                }
                stage('three'){
                    when{
                        not{
                            branch "master"
                        }
                    }
                    steps{
                        echo "Hello"
                    }
                }
                stage('four'){
                    parallel {
                        stage('Unit Test'){
                            steps{
                                echo "Running the unit test..."
                            }
                        }
                        stage('Integration Test'){
                            agent {
                                docker {
                                    reuseNode false
                                    image 'ubuntu'
                                }
                            }
                            steps {
                                echo "Running the integration test..."
                            }
                        }
                    }
                }
            }
}
    