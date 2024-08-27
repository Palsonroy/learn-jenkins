    pipeline {
        agent {
        node {
            label 'AGENT-1'
            
        }
    }
    environment { 
            GREETINGS = 'Hello-Jenkins'
        }
        stages {
            stage('Example Build') {
                steps {
                    echo 'Hello World'
                }
            }
            stage('Example Deploy') {
                when {
                    branch 'production'
                }
                steps {
                    echo 'Deploying'
                }
            }
            stage('greeting') {
                steps {
                    sh """
                        echo "Here i wrote shell script"
                        env
                    """
                }
            }
        
        
        }

        post { 
            always { 
                echo 'I will always say Hello again!'
            }
        }
    }