pipeline {
    agent any
    environment {
        env_url='pipeline.google.com'
        env_cred= credentials('ssh_cred')             
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
    

    
