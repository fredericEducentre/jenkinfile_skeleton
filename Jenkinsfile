pipeline {
    // Définition des options globales du pipeline
    agent any // Utilise n'importe quel agent disponible pour exécuter le pipeline
    // Pour ajouter un agent specifique décommenter la ligne suivante et supprimer celle du dessus
    /*
    agent {
        label 'nom_de_l_agent'
    }
    */

    // Stages du pipeline
    stages {
        // Stage de clonage du code depuis un référentiel Git
        stage('Clonage du Code') {
            steps {
                // Suppression du dossier précédent si existant
                deleteDir()
                // Étape de clonage du code depuis un dépôt Git
                git branch: 'main', url: 'URL_du_repo'
            }
        }

        // Stage de construction du projet
        stage('Construction') {
            steps {
                sh 'ma command de build'
            }
        }

        // Stage de déploiement
        stage('Test') {
            steps {
                sh 'ma commande de test'
            }
        }
    }

    // Post-actions à exécuter après la fin du pipeline
    post {
        // Action à exécuter en cas d'échec du pipeline
        failure {
            // Exemple: Notification en cas d'échec du pipeline
            echo 'Le pipeline a échoué. Veuillez vérifier les logs pour plus d\'informations.'
        }

        // Action à exécuter en cas de succès du pipeline
        success {
            // Exemple: Notification en cas de succès du pipeline
            echo 'Le pipeline a réussi. Le déploiement a été effectué avec succès.'
        }
    }
}
