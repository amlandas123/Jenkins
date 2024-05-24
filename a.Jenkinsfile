pipeline{
    agent any
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