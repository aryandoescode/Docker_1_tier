pipeline {
    agent any

    stages {
        stage('clean')
        {
            steps{
                cleanWs()
            }
        }
        stage('Git Checkout')
        {
            steps {
                script{
                    git branch: 'main', url: 'https://github.com/aryandoescode/Docker_1_tier.git'
                }
            }
        }
        
        stage('Image Build') {
            steps {
            sh 'docker image build -t apa:1 .'
            }
        }
        stage('Docker Run') {
            steps {
            sh 'docker run -d -p 6969:80 apa:1'
            }
        }
    }
}
