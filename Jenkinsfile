pipeline {
    agent any
    environment {
         nom = 'bolos'
        prenom = 'MDRRRRRRRRRRRRRRRRRRRRRRR'
    }
    options {
        retry(2)
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: "On s'en tape de la description")
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('Example') {
            options {
                timeout(time: 1, unit: 'SECONDS')
            }
            steps {
                echo 'Hello World'
                echo nom
            }
        }
            stage('maven version') {
                steps {
                    script{
                        sh 'mvn --version'
                    }
                }
            }
        stage('Example2') {
            steps {
                echo prenom
                echo nom
            }
        }
    }
    post { 
        always { 
            echo 'cest cooooool!'
            echo "Password: ${params.PASSWORD}"
        }
    }
}