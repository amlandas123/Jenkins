pipeline {
    agent any
    environment {
        env_url='pipeline.google.com'
        env_cred= credentials('ssh_cred')             
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        // choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        // password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    // triggers { cron('*/1 * * * *') }
    
    triggers { pollSCM('*/1 * * * *') }
    
    options { 
        buildDiscarder(logRotator(numToKeepStr: '10')) 
        timeout(time: 5, unit: 'MINUTES')
    }

    tools {
        maven 'maven-394' 
        ant 'ant-11011'
    }

    stages {
        stage ('Name of the stage = 1'){
            steps {
                sh "echo Hello everyone"
                sh 'uptime'
                sh 'df -hT'
                sh 'echo "Name of the Variable is ${env_url}"'
                sh "env"
            }
        }

        stage ('Name of the stage = 2'){
            environment{
                task_url='pipeline.internal.com'
            }
            steps {
                sh "echo Keep your hard work"
                sh "hostname"
                sh 'echo "Name of the Variable is ${task_url}"'
                sh "touch file1.txt"
            }
        }

        stage('name of the stage = 3') {
            steps {
                sh 'mvn --version'
                sh 'ant -version'
            }
        }

        stage ('Name of the stage = 4'){
            environment{
                web_url='www.dimple.co.in'
            }
            steps {
                 sh "free -m"
                 sh 'echo "Hello the stage 3 variable is ${web_url}"'
                 sh "echo This is the 3rd stage printing"   
                 sh "echo The Global Variable is ${env_url}"
            }

        }
        stage ('Demo on Parallel Job'){
            parallel{
                stage ('Executing 1') {
                    steps {
                        sh "echo Download is in progress"
                        sh "sleep 120"
                    }
                }
                stage ('Executing 2') {
                    steps {
                        sh "ehco Download is in progress"
                        sh "sleep 120"
                    }
                }
                stage ('Executing 3'){
                    steps {
                        sh "echo Download is in progress"
                        sh "sleep 120"
                    }
                }
            }
        }
    }    
}
    

    
