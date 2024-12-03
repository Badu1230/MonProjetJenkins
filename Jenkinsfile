pipeline {
    agent any
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
                        withEnv([
                            "JAVA_HOME=C:\\Program Files\\Eclipse Adoptium\\jdk-17.0.13.11-hotspot",
                            "PYTHON_HOME=C:\\Users\\Badu\\Documents\\python-3.13",
                            "PATH=${env.PATH}:${JAVA_HOME}/bin:${PYTHON_HOME}"
                        ]) {
                            sh 'echo "Running on Unix"'
                            sh 'javac HelloWorld.java'
                            sh 'java HelloWorld'
                            sh 'python3 hello.py'
                        }
                    } else {
                        withEnv([
                            "JAVA_HOME=C:\\Program Files\\Eclipse Adoptium\\jdk-17.0.13.11-hotspot",
                            "PYTHON_HOME=C:\\Users\\Badu\\Documents\\python-3.13",
                            "PATH=${env.PATH};${JAVA_HOME}\\bin;${PYTHON_HOME}"
                        ]) {
                            bat 'echo "Running on Windows"'
                            bat 'javac HelloWorld.java'
                            bat 'java HelloWorld'
                            bat 'python hello.py'
                        }
                    }
                }
            }
        }
    }
}
