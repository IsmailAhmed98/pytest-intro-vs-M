pipeline{
    agent any
    triggers{
        pollSCM('* * * * *')
    }
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
        withSonarQubeEnv('SONARQUBE'){
            sh 'python3 ops.py sonar:sonar -Dsonar.organization=ismailahmed'
        }
        stage('Test') {
            steps {
                sh '''pip install pytest
                python3 -m pytest'''
            }
        }
    }

}