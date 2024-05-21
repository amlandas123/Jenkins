pipeline{
    agent any
    environment{
        env_var = "www.google.com"
    }
    
    stages{
        stage("A"){
            steps{
                sh 'uptime'
                sh "echo name of the url is ${env_var}"
            }
        }
    }
}    