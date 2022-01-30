# md
<!-- Output copied to clipboard! -->

<!-----

Yay, no errors, warnings, or alerts!

Conversion time: 0.526 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β33
* Sun Jan 30 2022 09:30:32 GMT-0800 (PST)
* Source doc: TP1-INF6150
----->



    **A -**  **(5 pts) Exigences détaillées dans GitLab**



1. Au moment de la création d'un nouvel utilisateur, _nous avons des données aléatoires dans la section de profil_. Si nous changeons ses informations pour nos informations personnelles et que nous quittons l’application pour revenir, rien n’a été sauvegardé. Nous sommes obligé de ressaisir nos informations dans le profil ainsi que le poid dans la section poid.

_	**<span style="text-decoration:underline;">Bénéfice :</span>**_



* Le client ne va pas perdre son temps à ressaisir ses informations initiales.
* La communication entre le back-End et la BD sera optimisée
2. Nous avons constaté un problème lorsque la préférence était sauvegarder en lbs et non en kg. Au moment de quitter l’application et de se reconnecter, le poids avait été divisé par 2,2.  
    * Nous devons corriger la logique de conversion du poid en kg
    * Au moment de quitter l’application, il est normal de reconvertir les données en kg, mais si nous devons les faire afficher en lbs, on doit multiplier par 2,2 et non diviser le nombre par 2,2. Nous n’avons pas de problème si nous sauvegardons la préférence du poids en kg bien sûr.

**_<span style="text-decoration:underline;">Bénéfice :</span>_**



* Le client va pouvoir garder ses données stables et voir mieux sa progression au niveau de son poids dans le graphique (meilleur visuel graphique) 
* La communication entre le back-End et la BD sera optimisée
* Améliorer la logique de la programmation. 
3. Au moment de créer le profil, il devrait y avoir dans section profil, un champ pour saisir le poids initial qui irait se transposer dans la section du poids automatiquement et mettrait le champ «poids initial» non modifiable. Il faudrait aussi un champ pour le poids cible dans la même séquence.

**_<span style="text-decoration:underline;">Bénéfice :</span>_**



* Amélioration de l’interface utilisateur. Un meilleur suivi pour l’utilisateur.
* Le contrôle dès le départ des bonnes informations en BD. Meilleure communication entre le back-End et la BD sera optimisée
* Améliorer la logique de programmation. 
4. Une fois le point 3 terminé, on va pouvoir implémenter dans le graphique les points rouges et vert qui correspondent au poids initial et au poids cible respectivement.

**_<span style="text-decoration:underline;">Bénéfice :</span>_**



* Amélioration du graphique sur la progression du poids avec le poids initial et le poids cible à atteindre pour l’utilisateur.
* Ce qui permettra à ce dernier de suivre correctement la progression de son poids et de son IMC au fur et à mesure que son poids se rapproche de son poids cible.
* Meilleure communication entre le back-End et la BD sera optimisée
* Améliorer la logique de la programmation.
5. Réorganisation de la section poids.
    * _Explication : _
        * Le champ pour saisir le poids devrait être tout de suite après le «label» Poids et la section IMC devrait suivre à droite
        * Éliminer les flèches qui apparaissent à droite du champ IMC. IMC est un calcul en arrière-plan de l’application.

**_<span style="text-decoration:underline;">Bénéfice :</span>_**



* Amélioration du visuel de la section Poids.
6. Si le champ «taille» ou dans le champ «poids» sont vides, le champ «IMC» demeure vide. Il faudrait avoir un message d’avertissement.l
    * _Explication: _
        * Indiquer un message d’erreur : "IMC invalide! Vérifier les données de la taille et du poids de l’utilisateur.”
7. Une amélioration au niveau de l’importation des modules du poids dans app.js serait envisageable car l’affichage de certaines fonctionnalités reliées au poids est manquant. 
8. Un «refactoring» de code est nécessaire pour éliminer les avertissements indiqués dans la console où nous avions démarré le programme ou avec SonarQube.

**_<span style="text-decoration:underline;">Bénéfice pour les exigences 7 et 8:</span>_**



* Correction de code smells, amélioration du design visuel de la section poids
9. Suggestion d'implémentation des langues française et anglaise dans le module poids
* Meilleure compréhension de l’application par l’utilisateur

    


    **B -**  **(3 pts) Scénarios opérationnels et** **tests**

* A partir des fichiers de l’application, on peut affirmer que la couverture de tests actuelle liée à la section poids est de 0%. Il n’existe pour le moment aucune donnée de tests qui permettrait de vérifier la bonne fonctionnalité des méthodes liées au poids.
* La couverture de tests cible devrait être composée de:
    * La conversion correcte du poids de Kg en Livres et vice versa
    * Un rendu parfait de la section poids avec toutes les fonctionnalites necessaires à la saisie et l’affichage des données du poids concernant l’utilisateur
    * Obtenir les données reliées au poids actuel, au poids cible et au poids initial depuis la base de données
    * Lorsque l’utilisateur change la valeur de son poids cible selon son besoin, l’application doit pouvoir enregistrer correctement la nouvelle donnée. 
    * La vérification de l’IMC, à partir de la taille et du poids fourni par l’utilisateur.
    * L'évolution du graphe en fonction des différents poids et des dates initiale et  cible



**C -**  **(2 pts) Données requises et impactées**

_<span style="text-decoration:underline;">Calculer l’IMC </span>_

_Données requises:_

-> Taille de l’utilisateur (paramètre obtenu via la base de donnée, données en entrée lors de la première connexion de l’utilisateur)

_Données produites:_

-> Calcul de l’IMC à afficher dans sa section correspondante, enregistrement de la donnée dans la base de données du client.

_<span style="text-decoration:underline;">Enregistrer le poids Initial:</span>_

_Données requises:_

-> Saisie de la donne du poids dans le champ poids initial

_Données produites:_

-> Enregistrement dans la base de données, mise à jour dans la section graphique du poids initial: ceci pourrait modifier l’affichage des données. 

_<span style="text-decoration:underline;">Conversion du poids de Kg en Livres</span>_

_Données requises:_

-> Saisie de la donnée du poids

_Données produites:_

-> Obtenir la donnée du poids, l’envoyer vers la fonctionnalité de conversion des poids, Modifier la donnée dans la section poids de l’application.

_<span style="text-decoration:underline;">Design du graphique évolutif du poids </span>_

_Données requises:_

-> via la base de données, obtenir les différents poids initial, actuel et cible

_Données produites:_

-> Envoyer les données à la fonctionnalité d’affichage du graphique détaillant l'évolution du poids de l’utilisateur.
