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
                sh'echo dckr_pat_tpK-eSkoivTX2ip34AVUonbA2aI | docker login -u rishikeshkumar5147 --password-stdin'
            }
        }
        stage('Docker image push ') {
            steps {
                sh'docker image push rishikeshkumar5147/httpjenkins'
            }
        }
        stage('Remove Container') {
            steps {
                sh'docker container rm --force mywebsite'
            }
        }
                stage('Run COntainer ') {
            steps {
                sh'docker container run -d --name mywebsite -p 9090:80  rishikeshkumar5147/httpjenkins'
            }
        }
    }
}

