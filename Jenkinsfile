pipeline {
    agent any
    environment{
        name='subhash'
    }
    parameters{
        string(name:'person', defaultValue: 'Subhash Kumar Jha', description: "who are you?")
        booleanParam(name:'isMale', defaultValue: true, description: "")
        choice(name:'City', choices: ['Delhi','Jaipur','Mumbai','Pune'], description: "")
    }

    stages {
        stage('Run A Commnad') {
            steps {
                bat '''
                    dir
                    cd
                    date /t
                    time /t
                '''
            }
        }
        stage('Environment Variable') {
            environment{
                user_name='javatechiesubhash'
            }
            steps {
                bat 'set name'
                bat 'echo %BUILD_ID%'
                bat 'echo %user_name%'
            }
        }
        stage('Parameters') {
            steps {
                echo 'Deploy on test..'
                bat 'echo %user_name%'
                bat 'echo %person%'
            }
        }
        stage('Continue ?') {
            input{
                message "Should we continue?"
                ok "Yes we should"
            }
            steps {
                echo 'Deploy on prod..'
            }
        }
        stage('Deploy on prod') {
            steps {
                echo 'Deploy on prod..'
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure{
            echo 'Failure'
        }
        success{
             echo 'Success'
        }
    }
}
