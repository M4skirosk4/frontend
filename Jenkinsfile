pipeline {
    agent any

    stages {
        stage('Clonar Repositorio') {
            steps {
                git 'https://github.com/M4skirosk4/frontend.git'
            }
        }

        stage('Instalar Dependencias') {
            steps {
                script {
                    sh 'npm install'
                }
            }
        }

        stage('Ejecutar Pruebas') {
            steps {
                script {
                    sh 'npm run test'
                }
            }
        }

        stage('Construir') {
            steps {
                script {
                    sh 'npm run serve'
                }
            }
        }
    }
}
