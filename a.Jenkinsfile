pipeline{
    agent any

    triggers { 
        pollSCM('*/1 * * * *') 
    }

    tools {
        maven 'apache-maven-3.9.0' 
    }
    parameters {
        choice(name: 'env', choices: ['dev', 'prod'], description: 'Pick something')
        choice(name: 'component', choices: ['frontend', 'user', 'shipping'], description: 'Pick something')
       
    }
    options { buildDiscarder(logRotator(numToKeepStr: '5')) 
              timeout(time: 4, unit: 'MINUTES')   
    
    }

    environment{
        env_var = "www.google.com"
        place_var = "Mumbai"
    }
    
    stages{
        stage("This is first"){
            steps{
                sh 'mvn --version'
                sh "echo name of the url is ${env_var}"
                sh "sleep 150"
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