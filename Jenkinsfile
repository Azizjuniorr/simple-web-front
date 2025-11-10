pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Récupération du code source depuis GitHub...'
                git 'https://github.com/username/simple-web-front.git'
            }
        }

        stage('Verify Files') {
            steps {
                echo 'Vérification que les fichiers existent...'
                bat 'dir'        // sous Windows remplacer par : bat 'dir'
            }
        }

        stage('Archive Website') {
            steps {
                echo 'Archivage des fichiers du site...'
                archiveArtifacts artifacts: '**/*', fingerprint: true
            }
        }
    }

    post {
        success {
            echo "Build réussi : Le site statique est archivé et disponible !"
        }
        failure {
            echo "Échec du pipeline."
        }
    }
}
