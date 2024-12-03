pipeline {
    agent any

    environment {
        // Chemin vers l'installation de Java 17
        JAVA_HOME = "C:\\Program Files\\Eclipse Adoptium\\jdk-17.0.13.11-hotspot"
        // Chemin vers l'installation de Python (ajustez si nécessaire)
        PYTHON_HOME = "C:\\Users\\Badu\\Documents\\python-3.13"
        PATH = "${JAVA_HOME}\\bin;${PYTHON_HOME};${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Clonage du dépôt..."
                git branch: 'main', url: 'https://github.com/Badu1230/MonProjetJenkins.git'
            }
        }

        stage('Build Java Code') {
            steps {
                script {
                    echo "Compilation du code Java avec Java 17..."
                    bat 'javac HelloWorld.java' // Compile le code Java
                }
            }
        }

        stage('Run Java Code') {
            steps {
                script {
                    echo "Exécution du code Java avec Java 17..."
                    bat 'java -version' // Affiche la version de Java
                    bat 'javac -version' // Affiche la version du compilateur
                    bat 'java HelloWorld' // Exécute le code Java
                }
            }
        }

        stage('Run Python Script') {
            steps {
                script {
                    echo "Exécution du script Python..."
                    bat 'python --version' // Vérifie la version de Python
                    bat 'python hello.py' // Exécute le script Python
                }
            }
        }
    }

    post {
        always {
            echo "Exécution du pipeline terminée."
        }
        success {
            echo "Compilation et exécution réussies !"
        }
        failure {
            echo "Une erreur est survenue pendant la compilation ou l'exécution."
        }
    }
}
