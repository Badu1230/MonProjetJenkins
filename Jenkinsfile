pipeline {
    agent any
    environment {
        // Set JAVA_HOME to Java 17 directory (update with your actual path)
        JAVA_HOME = "C:\\Program Files\\AdoptOpenJDK\\jdk-17.0.13" // Adjust this path as per your Java installation
        // Set PYTHON_HOME to the path of your Python installation
        PYTHON_HOME = "C:\\path\\to\\python" // Replace with your actual Python installation path
        // Update PATH to include both Java and Python binaries
        PATH = "${JAVA_HOME}\\bin;${PYTHON_HOME};${env.PATH}"
    }
    stages {
        // Stage to checkout the code from the GitHub repository
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Badu1230/MonProjetJenkins.git'
            }
        }
        
        // Stage to build the Java code
        stage('Build Java Code') {
            steps {
                script {
                    echo "Compiling Java code with Java 17"
                    bat 'javac HelloWorld.java' // Compile Java code using Java 17
                }
            }
        }

        // Stage to run the Java code
        stage('Run Java Code') {
            steps {
                script {
                    echo "Running Java code with Java 17"
                    bat 'java HelloWorld' // Run the compiled Java program using Java 17
                }
            }
        }

        // Stage to run the Python script
        stage('Run Python Script') {
            steps {
                script {
                    echo "Running Python script"
                    bat 'python hello.py' // Run Python script
                }
            }
        }
    }
    post {
        always {
            // Clean up or notify if needed after the pipeline completes
            echo "Pipeline execution completed."
        }
        success {
            // Actions on successful completion of the pipeline
            echo "Build and Execution completed successfully!"
        }
        failure {
            // Actions on failure
            echo "There was an error during the build or execution."
        }
    }
}
