// Fichier: Jenkinsfile
pipeline {
    agent any // Exécute sur n'importe quel agent Jenkins disponible

    stages {
        // Stage 1: Checkout (Généralement implicite si Pipeline depuis SCM)
        // Jenkins checkout automatiquement le code source contenant ce Jenkinsfile
        // avant de démarrer le pipeline lorsqu'il est configuré en "Pipeline script from SCM".
        // L'étape 'git' explicite est souvent redondante dans ce cas.
        // Si vous aviez besoin de récupérer un autre dépôt ou une branche spécifique
        // ici, vous utiliseriez 'checkout scm' ou un 'git' plus complet avec credentialsId.
        // Pour cet exemple simple, nous nous fions au checkout initial.

        stage('Build') {
            steps {
                // Affiche simplement un message. Remplacez par vos commandes de build réelles.
                // 'sh' exécute des commandes shell (Linux/macOS). Utilisez 'bat' pour Windows.
                sh 'echo "Building the project..."'
                sh 'echo "Using Git version:"'
                sh 'git --version' // Exemple pour montrer que git est dispo
            }
        }

        stage('Test') {
            steps {
                // Affiche simplement un message. Remplacez par vos commandes de test réelles.
                sh 'echo "Running tests..."'
                // Exemple : sh './run-tests.sh'
            }
        }

        // Ajoutez d'autres stages si nécessaire : Deploy, Analyse de code, etc.
        // stage('Deploy') {
        //     steps {
        //         sh 'echo "Deploying..."'
        //     }
        // }
    }

    // Optionnel : Actions à exécuter à la fin du build, quel que soit le résultat
     post {
         always {
             echo 'Pipeline finished.'
              cleanWs()  //Nettoyer l'espace de travail
         }
         success {
             echo 'Pipeline succeeded!'
         }
         failure {
             echo 'Pipeline failed!'
         }
     }
}