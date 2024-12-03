# Intra D30 David Savard

## Instructions - Créer un Pipeline Jenkins

1. **Configuration du dépôt GitHub**

   Créez un dépôt GitHub avec la structure proposée :

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

   # 📌 **⬜ Votre imprime-écran ici (10 points) :** 
  

3. **Environnement d'exécution**

   # 📌 **⬜ Votre réponse ici (10 points) :**  
   _(Indiquez votre environnement d'exécution (Windows, Linux, ou Docker) et justifiez brièvement votre choix.)_

4. **Création du Jenkinsfile**

   # 📌 **⬜ Votre réponse ici (10 points) :**  
   _(Écrivez votre Jenkinsfile complet ici. Assurez-vous qu'il exécute les deux scripts et se déclenche à chaque modification des fichiers spécifiés.)_

5. **Vérification des sorties dans la console**

   # 📌 **⬜ Votre imprime-écran ici (10 points) :** 
   _(Insérez une capture d'écran montrant l'exécution des deux scripts (Java et Python) dans la console Jenkins suite à une exécution manuelle.)_




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
