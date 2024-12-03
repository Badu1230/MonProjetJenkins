pipeline {
    agent any
    environment {
        JAVA_HOME = "C:\\Program Files\\Eclipse Adoptium\\jdk-17.0.13.11-hotspot" 
        PYTHON_HOME = "C:\\Users\\Badu\\Documents\\python-3.13" 
        PATH = "${JAVA_HOME}\\bin;${PYTHON_HOME};${env.PATH}"
    }
    stages {
        stage('Checkout') {
            steps {
                echo "Clonage du dépôt Git"
                git branch: 'main', url: 'https://github.com/Badu1230/MonProjetJenkins.git'
            }
        }

        stage('Build Java Code') {
            steps {
                script {
                    echo "Compilation du code Java avec Java 17"
                    bat 'javac HelloWorld.java' // Compilation du code Java
                }
            }
        }

        stage('Run Java Code') {
            steps {
                script {
                    echo "Exécution du code Java avec Java 17"
                    bat 'java -version' // Vérification de la version de Java utilisée
                    bat 'javac -version' // Vérification de la version du compilateur Java
                    bat 'java HelloWorld' // Exécution du code Java
                }
            }
        }

        stage('Run Python Script') {
            steps {
                script {
                    echo "Exécution du script Python"
                    bat 'python hello_world.py' // Exécution du script Python
                }
            }
        }
    }

    post {
        always {
            echo "Execution du pipeline terminee."
        }
        success {
            echo "Compilation et execution terminees avec succes !"
        }
        failure {
            echo "Une erreur est survenue pendant la compilation ou l execution."
        }
    }
}
