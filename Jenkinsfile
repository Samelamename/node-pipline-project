pipeline{
    agent any
    stages {
        stage('init'){
            steps {
                sh 'docker stop nodejs-project || true'
                sh 'docker rm nodejs-project || true'
            }
        }
        stage('build'){
            steps {
                sh 'docker BUILD -T nodejs-project:${BUILD_NUMBER} .'
            }
        }
        stage('run'){
            steps {
                sh 'docker run -p 80:5000 --name nodejs -d nodejs-project:${BUILD_NUMBER}'
            }
        }
    }
}