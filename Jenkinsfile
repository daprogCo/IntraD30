pipeline {
    agent any
    stages {
        stage('Run Script') {
            steps {
                sh 'javac HelloWorld.java && java HelloWorld'
                sh 'echo "Le nom du job est ${JOB_NAME}"'
                sh 'echo "Le numéro du build est ${BUILD_NUMBER}"'
                sh 'echo "Le chemin complet vers le répertoire est ${WORKSPACE}"'
                sh 'echo "Voici toutes les variables d environnement : ${env}"'
                sh 'python3 hello_world.py'
            }
        }
    }
}