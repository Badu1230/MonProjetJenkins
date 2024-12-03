pipeline {
    agent any
    environment {
        // Set the JAVA_HOME to Java 17 directory
        JAVA_HOME = "C:\\Program Files\\Eclipse Adoptium\\jdk-17.0.13.11-hotspot" // Adjust to your actual Java path
        PYTHON_HOME = "C:\\Users\\Badu\\AppData\\Local\\Microsoft\\WindowsApps" // Replace with your actual Python installation path
        PATH = "${JAVA_HOME}\\bin;${PYTHON_HOME};${env.PATH}"
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Badu1230/MonProjetJenkins.git'
            }
        }

        stage('Build Java Code') {
            steps {
                script {
                    echo "Compiling Java code with Java 17"
                    bat 'javac HelloWorld.java'  // Compile Java code
                }
            }
        }

        stage('Run Java Code') {
            steps {
                script {
                    echo "Running Java code with Java 17"
                    bat 'java -version' // Verify the Java version being used
                    bat 'javac -version' // Verify the Java compiler version
                    bat 'java HelloWorld'  // Run Java code
                }
            }
        }

        stage('Run Python Script') {
            steps {
                script {
                    echo "Running Python script"
                    bat 'python hello.py'  // Run Python script
                }
            }
        }
    }

    post {
        always {
            echo "Pipeline execution completed."
        }
        success {
            echo "Build and Execution completed successfully!"
        }
        failure {
            echo "There was an error during the build or execution."
        }
    }
}
