pipeline {
    agent any

    stages {
        stage('clean')
        {
            steps{
                cleanWs()
            }
        }
        stage('Git Clone') {
            steps {
            sh 'git clone https://github.com/aryandoescode/Docker_1_tier.git'
            }
        }
        stage('Permission') {
            steps {
            sh 'sudo chmod 666 /var/run/docker.sock'
            }
        }
        stage('Image Build') {
            steps {
            sh 'docker image build -t apa:1 /var/lib/jenkins/workspace/Docker/Docker_1_tier'
            }
        }
        stage('Docker Run') {
            steps {
            sh 'docker run -d -p 6969:80 apa:1'
            }
        }
    }
}
