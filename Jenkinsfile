    pipeline {
        agent {
        node {
            label 'AGENT'
            
        }
    }
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 1 , unit: 'SECONDS')
    }
     parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
            stage('Example') {
                steps {
                     sh """
                        echo "Hello ${params.PERSON}"

                        echo "Biography: ${params.BIOGRAPHY}"

                        echo "Toggle: ${params.TOGGLE}"

                        echo "Choice: ${params.CHOICE}"

                        echo "Password: ${params.PASSWORD}"
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