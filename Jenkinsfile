pipeline {
    agent any
    stages {
        stage('Run Python Script') {
            steps {
                sh 'python hello_world.py'
            }
        }
        stage('Run Java Script') {
            steps {
                sh 'javac HelloWorld.java && java HelloWorld'
            }
        }
    }
    triggers {
        pollSCM("* * * * *")  // Ceci permet de déclencher le pipeline à chaque changement dans le dépôt
    }
}
