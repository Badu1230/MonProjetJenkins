pipeline {
    agent any
    environment {
        JAVA_HOME = 'C:\\Program Files\\Java\\jre1.8.0_421'
        PYTHON_HOME = 'C:\\Users\\Badu\\AppData\\Local\\Microsoft\\WindowsApps'
        PATH = "${env.PATH};${JAVA_HOME}\\bin;${PYTHON_HOME}"
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Badu1230/MonProjetJenkins.git'
            }
        }
        stage('Build') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'javac HelloWorld.java && java HelloWorld'
                        sh 'python3 hello.py'
                    } else {
                        bat 'javac HelloWorld.java && java HelloWorld'
                        bat 'python hello.py'
                    }
                }
            }
        }
    }
}
