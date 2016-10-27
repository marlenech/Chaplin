### 7 jours et 03h29 plus tard...

Ma conclusion de la semaine : j’ai passé beaucoup de temps sur le projet, mais le projet n’a pas avancé !

<img src = "http://www.reactiongifs.com/r/prc.gif"/>

La dernière fois, je vous ai quitté en vous expliquant qu’il fallait que je réfléchisse à la meilleure méthode, selon moi, de gestion des données de l’appli. J’ai donc comparé les différentes méthodes selon mes besoins.

Mes besoins, c’est :

-	Pouvoir mettre à jour les données facilement et rapidement, via une application Android dédiée,
-	Partager ces données avec l’appli finale de conversion, en temps réel, sans passer par une mise à jour de l’appli à chaque modification de données,
-	Pouvoir réutiliser ces données pour d’autres applicatifs éventuels.

Les méthodes de sauvegarde et de partage des données existantes disponibles sous Android (enfin… que je connais) sont :

-	SharedPreferences : sauvegarde les données au sein de l’application pour une réutilisation au sein de celle-ci, utilisé notamment pour la gestion des préférences de l’utilisateur. Exemple : activer ou désactiver la réception de notifications – Inconvénient : ne peut pas être partagé par d’autres applications ;
-	Stockage interne : le stockage des données se fait via un fichier interne à l’application, qui ne peut être utilisé que par celle-ci. Toute modification du fichier nécessite une mise à jour de l’application ;
-	Stockage externe : le stockage des données se fait via un fichier généré par l’application, qui peut être utilisé par d’autres applications. Toute modification du fichier nécessite une mise à jour de l’application que le créé ;
-	Stockage en base de données : tout mobile Android embarque une base de données SQLite, mais cette base est privée, et ne peut être accessible directement que par l’application l’ayant créée ;
-	ContentProvider : c’est un fournisseur de contenu qui permet de partager les données d’une application (stockées en base SQLite, fichier, sharedpreferences), mais là aussi, chaque modification de données nécessite une mise à jour de l’application qui créée le stockage ;
-	<span class="highlight-span">Le stockage en ligne : les données sont accessibles sur la web, via une connexion Internet. La mise à jour des données peut donc se faire de façon simple et rapide, en ligne, sans mise à jour de l’appli, tout en étant réutilisables par d’autres applicatifs…</span>

<img src="http://www.reactiongifs.com/r/hsk.gif"/>

Parfait ! Je vais donc stocker mes données en ligne. Et le moyen bien connu pour stocker ses données en ligne de manière fiable et ordonnée, c’est de passer par une <span class="highlight-span">base MySQL</span> (système de gestion de base de données couramment utilisé). Et cela tombe bien puisque je possède déjà une base MySQL en ligne, pour gérer notamment les données clients d’un de mes sites web.

En revanche, je n’ai jamais connecté une telle base à une appli Android. Alors, autant vous dire que cette semaine, j’ai lu du code, et encore du code, via des tutos et articles, pour comprendre comment fonctionnait Android face à ces bases.

Et là… ce n’est pas aussi simple que je le pensais. Android ne peut lire et utiliser directement les données d’une base de données stockée en ligne. Il est alors nécessaire de passer par plusieurs étapes avant qu’une application puisse afficher et lire ces données :

-	Créer un <span class="highlight-span">fichier PHP</span> (langage de programmation) capable de se connecter, lire, et modifier les données d’une base,
-	Etablir une connexion via l’application Android à ce script PHP,
-	Convertir (=parser) les données via l’application, en <span class="highlight-span">fichier JSON</span> (format d’échange de données via un fichier léger),
-	Lire le fichier JSON pour afficher les données, et modifier le fichier pour mettre à jour la base de données, tout ceci via l’application Android.

Et puis parmi ces étapes, il faut inclure d’autres étapes : créer la table au sein de la base MySQL nécessaire au projet, passer certaines tâches en arrière plan (comme la connexion et le parse) lors de l’exécution de l’appli, tester le fonctionnement du script PHP, supprimer les erreurs qui apparaissent à chaque <span class="highlight-span">compilation</span> (=compresser l’ensemble des fichiers d’une application ou un programme dans un format compréhensible pour l’ordinateur ou le système) dans le <span class="highlight-span">logcat</span> (= messages du système Android, ou autre, affichant les avertissements, erreurs et erreurs fatales générés lors de l’exécution d’une application).


Alors pour tout vous dire, j’ai écrit du code, je suis passée par ces différentes étapes, mais je ne suis pas parvenue pour le moment à afficher les données contenues dans ma base MySQL depuis mon appli Android.

<img src="http://www.reactiongifs.com/r/dsppntmnt.gif "/>

Il y a sans doute une étape que j’ai dû oublier, une anomalie dans mon code, une simple erreur sur le nom d’une variable… bref je bloque !

Mais coder c’est souvent passer par ces moments aussi, ces phases où l’on ne parvient pas à obtenir ce que l’on veut, y passer des heures, écrire et réécrire son code, compiler et recompiler, tester et encore tester le programme, s’endormir sur le problème, pour se réveiller, avec toujours aucune solution, et puis <span class="highlight-span">un beau matin</span>… ajouter dans son code un point virgule, une lettre dans une variable pour … enfin obtenir un résultat !!! C’est aussi ça le plaisir de coder ! Bon, je vous rassure, parfois la solution est bien plus compliquée.

Alors voilà, il ne me reste plus qu’à reprendre l’ensemble de mon code pour découvrir d’où provient mon anomalie. Je vous ferai bien entendu un petit compte-rendu de cette anomalie la prochaine fois, vous aurez alors peut être le droit de vous moquer de moi !

<img src="http://www.reactiongifs.com/r/pat1.gif"/>

A bientôt.
