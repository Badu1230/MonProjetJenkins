pipeline {
    agent any
    environment {
        // Définir des chemins communs pour les environnements
        JAVA_HOME_WINDOWS = "C:\\Program Files\\Java\\jdk-17"
        PYTHON_HOME_WINDOWS = "C:\\Users\\Badu\\AppData\\Local\\Microsoft\\WindowsApps"
        JAVA_HOME_UNIX = "/usr/lib/jvm/java-8-openjdk-amd64"
        PYTHON_HOME_UNIX = "/usr/bin"
    }
    stages {
        stage('Checkout') {
            steps {
                echo "Cloning the repository..."
                git branch: 'main', url: 'https://github.com/Badu1230/MonProjetJenkins.git'
            }
        }

        stage('Build and Execute') {
            steps {
                script {
                    if (isUnix()) {
                        // Configuration pour Unix/Linux
                        withEnv([
                            "JAVA_HOME=${JAVA_HOME_UNIX}",
                            "PYTHON_HOME=${PYTHON_HOME_UNIX}",
                            "PATH=${env.PATH}:${JAVA_HOME_UNIX}/bin:${PYTHON_HOME_UNIX}"
                        ]) {
                            sh 'echo "Running on Unix..."'
                            sh 'javac HelloWorld.java'
                            sh 'java HelloWorld'
                            sh 'python3 hello.py'
                        }
                    } else {
                        // Configuration pour Windows
                        withEnv([
                            "JAVA_HOME=${JAVA_HOME_WINDOWS}",
                            "PYTHON_HOME=${PYTHON_HOME_WINDOWS}",
                            "PATH=${env.PATH};${JAVA_HOME_WINDOWS}\\bin;${PYTHON_HOME_WINDOWS}"
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
}
