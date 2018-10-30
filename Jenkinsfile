pipeline {
    agent any 
        stages {
            stage('One'){
                steps{
                    echo "Hi"
                }
            }
            stage('Two'){
                steps{
                    input('Do you want to proceed ?')
                }
            }
            stage('Three'){
                when{
                    is {
                        branch "master"
                    }
                }
                steps{
                    echo "hello"
                }
            }
            stage('Four'){
                parallel{
                    stage('Unit Test'){
                        steps {
                        echo "Running the unit Test.........."
                    }
                    }
                    stage('Integration Test'){
                        agent {
                            docker{
                                reuseNode false
                                image 'ubuntu'
                            }
                        }
                        steps{
                            echo "Running the integration unit test........."
                        }
                    }
                    

                }
            }
     }
}
