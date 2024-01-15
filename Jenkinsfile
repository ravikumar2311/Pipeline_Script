pipeline {
    agent none
    stages {
	
	stage('Non-Parallel Stage') {
	    agent {
                        label "Master"
                }
        steps {
                echo 'This stage will be executed first'
                }
        }

	
        stage('Run Tests') {
            parallel {
                stage('Test On Windows') {
                    agent {
                        label "Windows_Node"
                    }
                    steps {
                        echo "Task1 on Windows"
                    }
                    
                }
                stage('Test On Master') {
                    agent {
                        label "Master"
                    }
                    steps {
						echo "Task1 on Master"
					}
                }
            }
        }
    }
}
