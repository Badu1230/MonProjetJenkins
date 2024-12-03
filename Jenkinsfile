pipeline {
    agent any
    stages {
        stage('Run Python Script') {
            steps {
                sh 'python hello.py'
            }
        }
        stage('Run Java Script') {
            steps {
                sh 'javac HelloWorld.java && java HelloWorld'
            }
        }
    }
}

