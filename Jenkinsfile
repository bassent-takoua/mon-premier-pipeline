pipeline {
    agent any

    parameters {
        string(name: 'NOM_UTILISATEUR', defaultValue: 'Etudiant', description: 'Nom de la personne qui execute le pipeline')
        choice(name: 'ENVIRONNEMENT', choices: ['Dev', 'Staging', 'Production'], description: 'Environnement cible')
    }

    environment {
        APPLICATION_NAME = 'MonProjetDevOps'
        RELEASE_VERSION = '1.0.0'
    }

    stages {
        stage('Checkout') {
            steps {
                echo '=== Étape 1 : Récupération du code ==='
            }
        }
        stage('Build') {
            steps {
                echo "=== Étape 2 : Compilation de ${env.APPLICATION_NAME} (v${env.RELEASE_VERSION}) ==="
            }
        }
        stage('Test') {
            steps {
                echo '=== Étape 3 : Tests unitaires ==='
            }
        }
        stage('Deploy') {
            steps {
                echo "=== Étape 4 : Déploiement sur ${params.ENVIRONNEMENT} par ${params.NOM_UTILISATEUR} ==="
            }
        }
    }

    post {
        success {
            echo '✅ Le pipeline s est execute avec succes !'
        }
        failure {
            echo '❌ Le pipeline a echoue.'
        }
        always {
            echo '🧹 Nettoyage du workspace termine.'
        }
    }
}
