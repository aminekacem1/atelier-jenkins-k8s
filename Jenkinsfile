pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Compiling C applications...'
                sh 'gcc -o serveur/serveur serveur/serveur.c'
                sh 'gcc -o client/client client/client.c'
            }
        }
        stage('Docker Build') {
            steps {
                echo 'Building Docker Images...'
                sh 'docker build -t aminekacem1/serveur:latest ./serveur'
                sh 'docker build -t aminekacem1/client:latest ./client'
            }
        }
    }
}
