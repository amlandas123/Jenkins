pipeline {
    agent any
    environment {
        env_url='pipeline.google.com'             #Global level variable
    }
    stages {
        stage ('Name of the stage = 1'){
            steps {
                sh "echo Hello everyone"
                sh 'uptime'
                sh 'df -hT'
                sh 'echo "Name of the Variable is ${env_url}"'
            }
        }
# Task Level Variable
        stage ('Name of the stage = 2'){
            environment{
                task_url='pipeline.internal.com'
            }
            steps {
                sh "echo Keep your hard work"
                sh "hostname"
                sh 'echo "Name of the Variable is ${task_url}"'
            }
        }
    }    
}
    

    
