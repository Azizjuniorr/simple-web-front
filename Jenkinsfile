pipeline {
    agent any

    stages {
       stage('Checkout Code') {
  steps {
    git branch: 'master',
        credentialsId: 'github-creds',
        url: 'https://github.com/Azizjuniorr/simple-web-front.git'
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
