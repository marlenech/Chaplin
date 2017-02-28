### 144 jours et 1h03 plus tard...

Deux mois se sont écoulés depuis mon dernier article, deux mois à finaliser l’année 2016 de mes dossiers clients, à passer mes dernières régularisations, à vérifier une dernière fois mes taux pour que la totalité des mes cotisations apparaissant sur mes dossiers correspondent bien aux cotisations à payer sur l’année, et passer enfin l’ensemble des déclarations annuelles attendues au 31 janvier, et puis se lancer dans le paramétrage des nouveaux taux et rubriques de cotisations 2017, tout en prenant en compte les exigences de la nouvelle norme déclarative « DSN phase 3 » (norme déclarative obligatoire depuis le 1er janvier 2017 auprès des caisses de retraite et prévoyance… qui ne sont pas prêtes à recevoir cette norme… si si !).

Pendant ce temps, l’avancement de mon projet d’appli…

<img src = "http://i.giphy.com/EoeZCXWwmMIH6.gif"/>

Heureusement, j’ai eu le temps de m’y pencher ces derniers jours. Je m’étais arrêtée à l’intégration de mes premières « CardView » lors de mon précédent article :

<img src = "https://marlenech.github.io/img/dec29.gif"/>

J’ai alors réfléchi à ce qu’il doit se passer lorsque l’utilisateur sélectionne une CardView. Lorsque l’utilisateur sélectionne la CardView, il entend obtenir un résultat en fonction des éléments qu’il renseigne dans l’appli. C’est pourquoi, avant d’obtenir un résultat, il est nécessaire de l’interroger sur les éléments indispensables pour le calcul et la fiabilité du résultat. Par exemple, pour convertir un salaire brut en net, il faut :

-	la catégorie du salarié (cadre ou non cadre),
-	le type de contrat (CDI ou CDD),
-	le temps de travail (temps complet ou temps partiel),
-	le salaire brut mensuel,
-	etc.

Sauf qu’en matière d’<a href="https://marlenech.github.io/2016/Penser-Exp%C3%A9rience-Utilisateur-!.html">UX</a>, je vous rappelle que l’utilisateur aime les applications rapides et simples. Il faut alors lui donner l’envie de répondre à ces interrogations. C’est pour cela que je me suis intéressée aux animations sous Android. Quoi de mieux qu’une petite animation sympa pour questionner l’utilisateur ? J’ai alors débuté mes recherches sur le sujet via Internet, j’ai suivi des tutos, testé des choses et encore des choses, commencé à ressentir la fatigue accumulée par le périple « DSN phase 3 » du boulot, détesté des choses et des tutos et enfin trouvé une solution alternative (et pouvoir réellement apprendre les animations sous Android une fois remise de ce périple) : les librairies !

<img src = "http://i.giphy.com/3o7ZeHqK4bCqCCAvv2.gif"/>

Une application Android, comme de nombreux programmes, est constituée d’un ensemble de fichiers. Ces fichiers ont chacun un rôle précis pour la bonne marche de l’application : les fichiers .xml vont permettre d’afficher les interfaces, les fichiers .java vont déterminer les actions à réaliser et/ou réalisables au sein de ces interfaces, etc. Parfois, la mise en place d’un élément dans une application peut alors demander de réaliser une multitude de fichiers pour son bon fonctionnement et ainsi nécessiter un certain nombre d’heures de travail. Une librairie va alors grandement simplifier les choses ! Elle permet d’intégrer très simplement un ensemble de fichiers proposant un ou plusieurs éléments à inclure dans notre application.

Dans mon cas, je souhaite animer du texte dans mes interfaces. J’ai alors trouvé cette petite librairie très simple d’utilisation et réalisant parfaitement ce qui m’aurait pris sans doute plusieurs heures à coder : <a href="https://github.com/hanks-zyh/HTextView">HTextView</a>

J’ai inclus une partie de mon code java dans une tâche asynchrone (= tâche séparée de l’activité principale de l’application) afin que le premier texte de mon interface s’anime au lancement puis, après un temps déterminé dans une tâche séparée, mon second texte s’affiche tout en s’animant.

Voici alors un premier rendu 


A bientôt !
