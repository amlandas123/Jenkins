pipeline{
    agent any
    parameters {
        // string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        // text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        // booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'env', choices: ['dev', 'prod'], description: 'Pick something')
        choice(name: 'component', choices: ['frontend', 'user', 'shipping'], description: 'Pick something')
        // password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    environment{
        env_var = "www.google.com"
        place_var = "Mumbai"
    }
    
    stages{
        stage("This is first"){
            steps{
                sh 'uptime'
                sh "echo name of the url is ${env_var}"
            }
        }
        stage("This is second"){
            steps{
                sh 'df -hT'
                sh "echo name of the city is ${place_var}"
            }
        }
        stage("This is third"){
            steps{
                sh 'hostnamectl'
            }
        }
    }
}    