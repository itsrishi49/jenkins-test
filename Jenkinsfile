pipeline {
    agent any

    stages {
        stage('Pull Git') {
            steps {
                git branch: 'main', url: 'https://github.com/itsrishi49/jenkins-test.git'
            }
        }
        stage('Image Build') {
            steps {
                sh'docker image build -t rishikeshkumar5147/httpjenkins .'
            }
        }
        stage('Docker Login') {
            steps {
                sh'echo  | docker login -u rishikeshkumar5147 --password-stdin'
            }
        }
        stage('Docker image push ') {
            steps {
                sh'docker image push 
            }
        }
        stage('Remove Container') {
            steps {
                sh'docker container rm --force mywebsite'
            }
        }
                stage('Run COntainer ') {
            steps {
                sh'docker container run -d --name mywebsite -p 9090:80  
            }
        }
    }
}

