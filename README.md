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

4. **Création du Jenkinsfile**
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

5. **Vérification des sorties dans la console**

   _(voir fichier **05_ConsoleOutput.txt** dans le dossier Steps)_

6. **Configuration et test du déclenchement automatique**

    _(voir fichier **06_CronJob.jpg** et **06_ConsoleOutput.txt** dans le dossier Steps)_

   Il suffit de sélectionner l'option **Build periodically** sous les choix **Build Trigger** et de parametrer la schédule avec le format CRON * * * * * représentant chaque minute, heure, jour, mois et tout les jours de la semaine.

7. **Variables d'environnement**
    
    _(voir fichier **07_ConsoleOutput.txt** dans le dossier Steps)_

   Plusieurs variables sont disponibles par défaut tel WORKSPACE, JOB_NAME ou BUILD_NUMBER.
   Certaines peuvent même être défini dans le Jenkinsfile.
   Celles-ci peuvent être appelé par la suite sous cette nomenclature ex.${WORKSPACE} 

8. **Configuration du Webhook GitHub**

   # 📌 **⬜ Votre réponse ici (10 points) :**  
   _(Détaillez les étapes pour configurer un webhook GitHub, y compris l'URL et l'activation de l'événement push.)_

11. **Test du Webhook**

   # 📌 **⬜ Votre imprime-écran ici (10 points) :**  
   _(Insérez une capture d'écran ou des logs du pipeline en cours d'exécution suite à une modification du README.md pour démontrer le bon fonctionnement du webhook.)_

11. **Méthodes de déclenchement d'un pipeline Jenkins**

    # 📌 **⬜ Votre réponse ici (10 points) :**  
    _(Expliquez les différentes méthodes de déclenchement d'un pipeline Jenkins suite à un push sur un dépôt Git, en comparant leurs avantages et inconvénients.)_

12. **Utilisation de Blue Ocean (Optionnel)**

    # 📌 **⬜ Votre réponse ici (10 points) :**  
    _(Si vous avez utilisé Blue Ocean, décrivez en détail la configuration effectuée pour atteindre les objectifs de l'exercice. Sinon, laissez cette section vide.)_
