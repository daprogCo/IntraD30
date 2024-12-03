pipeline {
    agent any
    stages {
        stage('Run Script') {
            steps {
                sh 'javac HelloWorld.java && java HelloWorld'
                sh 'echo "Hello World"'
                sh 'python3 hello_world.py'
            }
        }
    }
}