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
            }
        }
        
        stage ('Name of the stage == 3'){
            environment{
                web_url='www.dimple.co.in'
            }
            steps {
                 sh "free -m"
                 sh 'echo "Hello the stage 3 variable is ${web_url}"'
                 sh "echo This is the 3rd stage printing"   
            }

        }
    }    
}
    

    
