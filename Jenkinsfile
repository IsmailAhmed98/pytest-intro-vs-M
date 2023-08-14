pipeline{
    agent any
    stages{
        stage('clone'){
            steps{
                git branch:'main', url: 'https://github.com/IsmailAhmed98/pytest-intro-vs-M.git'
            }
        }
        stage('build'){
            steps{
                sh 'python3 ops.py'
            }
        }
        stage('Test') {
            steps {
                sh 'python3 -m pytest'
            }
        }
    }

}