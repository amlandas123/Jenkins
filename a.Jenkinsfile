pipeline{
    agent any

    triggers { 
        pollSCM('*/1 * * * *') 
    }

    tools {
        maven 'maven390' 
    }
    parameters {
        choice(name: 'env', choices: ['dev', 'prod'], description: 'Pick something')
        choice(name: 'component', choices: ['frontend', 'user', 'shipping'], description: 'Pick something')
       
    }
    options { buildDiscarder(logRotator(numToKeepStr: '5')) 
              timeout(time: 4, unit: 'MINUTES')   
    
    }

    environment{
        env_var = "www.facebook.com"
        place_var = "Mumbai"
    }
    
    stages{
        stage("This is first"){
            steps{
                sh 'mvn --version'
                sh "echo Welcome to Jenkins World"
                //sh "echo name of the url is ${env_var}"
                // sh "sleep 150"
            }
        }
        stage("This is second"){
            steps{
                sh 'df -hT'
                sh "echo name of the city is ${place_var}"
                sh "echo name of the url is ${env_var}"
            }
        }
        stage("This is third"){
            steps{
                sh 'hostnamectl'
            }
        }
        stage("Demo on parallel stages"){
            parallel{
                stage("Download-1"){
                    steps{
                        sh "echo Download-1 is in progress"
                        sh "sleep 120"
                }
            }
                stage("Download-2"){
                    steps{
                        sh "echo Download-2 is in progress"
                        sh "sleep 120"
                }

            }
                stage("Download-3"){
                    steps{
                        sh "echo Download-3 is in progress"
                }

            }
        }        
    }
    }
}    