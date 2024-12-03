# Intra D30 David Savard

## Instructions - Créer un Pipeline Jenkins

1. **Configuration du dépôt GitHub**
   _( voir fichier **01_Terminal_CommandesGit.jpg** )_

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
   _(voir fichier **05_ConsoleOutput.jpg** dans le dossier Steps)_

6. **Configuration et test du déclenchement automatique**

Dans cette section, on configure d'abord le déclenchement automatique, puis on le teste en effectuant une modification.

   6.1. **Configuration du déclenchement automatique**

   # 📌 **⬜ Votre réponse ici (10 points) :**  
   _(Expliquez en détail les étapes de configuration pour permettre le déclenchement automatique du pipeline suite à un push. Quesque nous devons changer ? )_

   6.2. **Test du déclenchement automatique**
   
   Modifiez le fichier `hello_world.py` comme suit :
   ```python
   print("Hello, World from Jenkins Pipeline! [Python]. This is <VOTRE NOM COMPLET ICI>")
   ```

   # 📌 **⬜ Votre imprime-écran ici (10 points) :**  
   _(Insérez une capture d'écran montrant l'exécution automatique du pipeline suite au push de cette modification.)_





7. **Variables d'environnement**

   # 📌 **⬜ Votre réponse ici (10 points) :**  
   _(Listez toutes les variables d'environnement utilisées, précisez leur rôle et fournissez les chemins correspondants.)_

8. **Configuration du Webhook GitHub**

   # 📌 **⬜ Votre réponse ici (10 points) :**  
   _(Détaillez les étapes pour configurer un webhook GitHub, y compris l'URL et l'activation de l'événement push.)_

9. **Test du Webhook**

   # 📌 **⬜ Votre imprime-écran ici (10 points) :**  
   _(Insérez une capture d'écran ou des logs du pipeline en cours d'exécution suite à une modification du README.md pour démontrer le bon fonctionnement du webhook.)_

10. **Méthodes de déclenchement d'un pipeline Jenkins**

    # 📌 **⬜ Votre réponse ici (10 points) :**  
    _(Expliquez les différentes méthodes de déclenchement d'un pipeline Jenkins suite à un push sur un dépôt Git, en comparant leurs avantages et inconvénients.)_

11. **Utilisation de Blue Ocean (Optionnel)**

    # 📌 **⬜ Votre réponse ici (10 points) :**  
    _(Si vous avez utilisé Blue Ocean, décrivez en détail la configuration effectuée pour atteindre les objectifs de l'exercice. Sinon, laissez cette section vide.)_
