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
        stage(checkout) {
            steps {
                git credentialsId: '708d0860-d5b9-4bad-b853-bc53d7ebf44b', url: 'https://github.com/BadBeerus/jenkinsfile.git'
            }
        }
    post { 
        always { 
            echo 'cest cooooool!'
            echo "Password: ${params.PASSWORD}"
        }
    }
}