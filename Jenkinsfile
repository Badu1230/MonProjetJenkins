pipeline {
    agent any
    environment {
        JAVA_HOME = "C:\\Program Files\\Eclipse Adoptium\\jdk-17.0.13.11-hotspot"  
        PYTHON_HOME = "C:\\Users\\Badu\\Documents\\python-3.13" 
        PATH = "${JAVA_HOME}\\bin;${PYTHON_HOME}\\Scripts;${env.PATH}"
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm  // Récupère le code du dépôt Git
            }
        }

        stage('Build Java Code') {
            steps {
                script {
                    echo "Compilation du code Java avec Java 17"
                    bat 'javac HelloWorld.java'  // Compile le code Java
                }
            }
        }

        stage('Run Java Code') {
            steps {
                script {
                    echo "Exécution du code Java avec Java 17"
                    bat 'java -version'  // Vérifie la version de Java
                    bat 'javac -version'  // Vérifie la version du compilateur Java
                    bat 'java HelloWorld'  // Exécute le code Java
                }
            }
        }

        stage('Run Python Script') {
            steps {
                script {
                    echo "Exécution du script Python"
                    bat 'python hello_world.py'  // Exécute le script Python avec le nom de fichier correct
                }
            }
        }
    }

    post {
        always {
            echo "L'exécution du pipeline est terminée."
        }
        success {
            echo "La compilation et l'exécution ont été réussies!"
        }
        failure {
            echo "Une erreur est survenue pendant la compilation ou l'exécution."
        }
    }
}
