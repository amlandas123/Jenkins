pipeline {
    agent any
    environment {
        env_url='pipeline.google.com'
    }
    stages {
        stage ('Name of the stage = 1'){
            steps {
                sh "echo Hello everyone"
                sh 'uptime'
                sh 'df -hT'
                sh 'Name of the Variable is $(env_url)'
            }
        }

        stage ('Name of the stage = 2'){
            steps {
                sh "echo Keep your hard work"
                sh "hostname"
            }
        }
    }    
}
    

    
