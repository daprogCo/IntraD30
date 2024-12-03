# Intra D30 David Savard

## Instructions - Créer un Pipeline Jenkins

1. **Configuration du dépôt GitHub**

    _( voir fichier **01_Terminal_CommandesGit.jpg** dans le dossier Steps)_

   Créez un dépôt GitHub avec la structure proposée :
    _(Git doit être installé localement)_

   ```bash
   mkdir IntraD30
   cd IntraD30
   touch HelloWorld.java hello_world.py Jenkinsfile README.md
   git init
   git add .
   git commit -m "Initial Commit"
   git remote add origin https://github.com/<your-account>/<your-repo>.git
   git branch -M master
   git push -u origin master
   ```

   Ajout les scripts suivants :

   - **HelloWorld.java :**
     ```java
     public class HelloWorld {
         public static void main(String[] args) {
             System.out.println("Hello, World from Jenkins Pipeline! [Java]");
         }
     }
     ```

   - **hello_world.py :**
     ```python
     print("Hello, World from Jenkins Pipeline! [Python]")
     ```

2. **Capture d'écran du dépôt GitHub**

    _(voir fichier **02_RepoGitHub.jpg** dans le dossier Steps)_
   
3. **Environnement d'exécution**

   _(voir fichier **03_ContainerJenkins.jpg** et **03_InstallPython3.txt** dans le dossier Steps)_

   J'ai utilisé un container Docker contenant Jenkins car c'est la facon moderne et la plus versatile pour déployer toute application.

5. **Création du Jenkinsfile**
   ```groovy
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
   ```

6. **Vérification des sorties dans la console**

   _(voir fichier **05_ConsoleOutput.txt** dans le dossier Steps)_

7. **Configuration et test du déclenchement automatique**

    _(voir fichier **06_CronJob.jpg** et **06_ConsoleOutput.txt** dans le dossier Steps)_

   Il suffit de sélectionner l'option **Build periodically** sous les choix **Build Trigger** et de parametrer la schédule avec le format CRON * * * * * représentant chaque minute, heure, jour, mois et tout les jours de la semaine.

8. **Variables d'environnement**
    
    _(voir fichier **07_ConsoleOutput.txt** dans le dossier Steps)_

   Plusieurs variables sont disponibles par défaut tel WORKSPACE, JOB_NAME ou BUILD_NUMBER.
   Certaines peuvent même être défini dans le Jenkinsfile.
   Celles-ci peuvent être appelé par la suite sous cette nomenclature ex.${WORKSPACE}

      ```groovy
      pipeline {
        agent any
        environment {
            MY_NAME = 'Dave the Dev'
        }
        stages {
            stage('Run Script') {
                steps {
                    sh 'javac HelloWorld.java && java HelloWorld'
                    sh 'echo "Le nom du job est ${JOB_NAME}"'
                    sh 'echo "Le numéro du build est ${BUILD_NUMBER}"'
                    sh 'echo "Le chemin complet vers le répertoire est ${WORKSPACE}"'
                    sh 'echo "Mon nom est: ${MY_NAME}"'
                    sh 'python3 hello_world.py'
                }
            }
        }
    }
   ```

10. **Configuration du Webhook GitHub**

    _(voir fichier **08_JenkinsTrigger.jpg** et **08_Webhook.jpg** dans le dossier Steps)_

11. **Test du Webhook**

    _(voir fichier **09_TestWebhook.jpg** dans le dossier Steps)_

12. **Méthodes de déclenchement d'un pipeline Jenkins**

    Il y a deux façons que nous avons explorer pour déclencher une pipeline Jenkins.
    1. Automatisation via un récurrence CRON qui assure que la pipeline déploie l'application à intervalle régulier sans la complexité impliqué par la configuration d'un webhook.
    2. Un webhook permet à la pipeline d'être déclenché seulement lorsqu'un changement est appliqué au répositoire et garantie que la solution déployé est toujours à jours.
