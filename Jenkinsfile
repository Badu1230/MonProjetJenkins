pipeline {
    agent any
    environment {
        PATH = "${env.PATH}:C:\\Users\\Badu\\AppData\\Local\\Microsoft\\WindowsApps"
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
                        sh 'echo "Running on Unix"'
                        // Add your Unix-specific build commands here
                    } else {
                        bat 'echo "Running on Windows"'
                        // Add your Windows-specific build commands here
                    }
                }
            }
        }
    }
}