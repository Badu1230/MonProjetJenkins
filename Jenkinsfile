pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Badu1230/MonProjetJenkins.git'
            }
        }
        stage('Build and Execute') {
            steps {
                script {
                    if (isUnix()) {
                        // Configuration Unix
                        withEnv([ 
                            "JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64", // Ajuste selon le besoin
                            "PYTHON_HOME=/usr/bin",
                            "PATH=${env.PATH}:${JAVA_HOME}/bin:${PYTHON_HOME}"
                        ]) {
                            sh 'echo "Running on Unix"'
                            sh 'javac HelloWorld.java'
                            sh 'java HelloWorld'
                            sh 'python3 hello.py'
                        }
                    } else {
                        // Configuration Windows avec Java 17 de Eclipse Adoptium
                        withEnv([ 
                            "JAVA_HOME=C:\\Program Files\\Eclipse Adoptium\\jdk-17.0.13.11-hotspot", 
                            "PYTHON_HOME=C:\\Users\\Badu\\AppData\\Local\\Microsoft\\WindowsApps", 
                            "PATH=${env.PATH};${JAVA_HOME}\\bin;${PYTHON_HOME}"
                        ]) {
                            bat 'echo "Running on Windows..."'
                            bat 'javac HelloWorld.java'
                            bat 'java HelloWorld'
                            bat 'python hello.py'
                        }
                    } 
            }
        }
    }
}
