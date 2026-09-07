pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Komalgorde/git-Jenkins-docker'
            }
        }
        //stage('Install Dependencies') {
         //   steps {
           //     sh ''' python3 -m venv venv
             //   ./venv/bin/pip install flask '''
            //}
        //}

        // stage('test') {
        //   steps {
        //     sh './venv/bin/python -m py_compile app.py'
        //}
        //}
        //stage('build') {
        //  steps {
        //    sh 'nohup ./venv/bin/python app.py > app.log 2>&1 &'
        //  sleep 5
        //sh 'curl http://localhost:5000'
        //}
        //}
        stage('build docker') {
            steps {
                sh 'docker build -t myapp:v2 .'
            }
        }
        stage('build image') {
            steps {
                sh 'docker images'
            }
        }
        stage('run container') {
            steps {
                sh 'docker run -d --name myapp -p 5000:5000 myapp:v2'
            }
        }
    }
}
