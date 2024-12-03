pipeline {
    agent any
    tools {
        // Ensure the correct JDK and Python versions are specified
        jdk 'JDK 17'
        python 'Python 3.13'
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
                        withEnv([
                            "JAVA_HOME=/usr/lib/jvm/jdk-17", 
                            "PYTHON_HOME=/usr/local/python-3.13",
                            "PATH=${env.PATH}:${JAVA_HOME}/bin:${PYTHON_HOME}/bin"
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
                            "PATH=${env.PATH};${JAVA_HOME}\\bin;${PYTHON_HOME}\\bin"
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
