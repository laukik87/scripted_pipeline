pipeline{
    agent none
    stages{
        stage('non-parallel Stage'){
            agent{label "Built-In_Node"}
            steps{echo 'this stage will be executed first from master node'}
        }

        stage('Run tests'){
            parallel{
                stage('Test on windows Node'){
                    agent{label 'Windows_Node'}
                    steps{echo 'Task1 on agent1'}
                }
                stage('Test on Master '){
                    agent{label 'Built-In_Node'}
                    steps{echo 'task2 on master'}
                }
            }
        }
    }
}
