pipeline {
    agent any

    tools {
        maven 'Maven'   // Asegúrate de que estos nombres coincidan con los configurados en Jenkins
        jdk 'JDK'
    }

    stages {
        stage('Clonar') {
            steps {
                git branch: 'main', url: 'https://github.com/malexa96/saludoapp.git'
            }
        }

        stage('Compilar') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Probar') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Empaquetar') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            echo "🎉 El build fue exitoso"
        }
        failure {
            echo "💥 El build falló"
        }
    }
}
