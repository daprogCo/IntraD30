pipeline {
    agent any
    stages {
        stage('Run Script') {
            steps {
                sh 'javac HelloWorld.java && java HelloWorld'
                sh 'echo "Le nom du job est ${env.JOB_NAME}"'
                sh 'echo "Le numéro du build est ${env.BUILD_NUMBER}"'
                sh 'echo "Le chemin complet vers le répertoire est ${env.WORKSPACE}"'
                sh 'python3 hello_world.py'
            }
        }
    }
}