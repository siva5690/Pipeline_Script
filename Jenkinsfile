pipeline {
    agent none
    stages {
	
	stage('Non-Parallel Stage') {
	    agent {
                        label "built-In Node"
                }
        steps {
                echo 'This stage will be executed first'
                }
        }

	
        stage('Run Tests') {
            parallel {
                stage('Test On Agent') {
                    agent {
                        label "delegate_node"
                    }
                    steps {
                        echo "Task1 on Agent"
                    }
                    
                }
                stage('Test On Master') {
                    agent {
                        label "Built-In Node"
                    }
                    steps {
						echo "Task1 on Master"
					}
                }
            }
        }
    }
}
