pipeline {
    agent any
    environment {
        JAVA_HOME = 'C:\\Program Files\\Java\\jre1.8.0_421'
        PYTHON_HOME = 'C:\\Users\\Badu\\AppData\\Local\\Microsoft\\WindowsApps'
        PATH = "${env.PATH};${JAVA_HOME}\\bin;${PYTHON_HOME}"
    }    
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

