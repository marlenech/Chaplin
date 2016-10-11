---
---

### Il y a quelques jours...

...j'ai pensé à une chose toute bête : réaliser un projet qui allie mon boulot à ma passion.

Mon boulot c'est gestionnaire de paie. Je réalise les bulletins de paie des salariés de divers secteurs, du boucher du quartier au gérant de multi-établissements. Ma passion personnelle, c'est le code, du Java au PHP en passant par le CSS, le Swift, etc.

Et puis j'ai pensé à débuter ce projet par un blog que voici, pour vous faire partager les différentes étapes de ce projet. 

### 3h32 plus tard...

> Le Projet : Une application Android qui convertit un salaire brut en net

Il existe plusieurs applications sur le store qui proposent ce type d'outils, mais la plupart fonctionnent sur la base d'un taux moyen de charges salariales et n'indiquent pas le taux de charges patronales. 

L'idée ici serait de renseigner les véritables taux et les mettre à jour via une base de données externe pour obtenir un algorithme plus fiable, en fonction de la situation du salarié, voir de son secteur d'activité.

> Le Fondement : 

Pou mener à bien le projet, il me faudra réaliser une première application, qui sera plutôt perso, pour me permettre de mettre à jour facilement la base de données contenant l'ensemble des taux et autres éléments. Je pourrais tout à fait ne pas passer par une appli et me contenter d'une page web, mais comme c'est un projet Android, autant rester sous Android jusqu'au bout. 

Pour celà, il me faut :

- créer une application avec un menu facile d'accès, répertoriant les différentes familles de taux et de données nécessaires à l'établissement d'un salaire,
- ouvrir une base de données externe, capable d'accueillir l'ensemble des éléments de salaire,
- programmer l'application pour qu'elle soit capable d'accéder à la base et qu'elle puisse la mettre à jour

Puis, il me restera à réaliser l'application publique, à publier sur le Play Store, proposant l'outil de conversion.

L'idée, c'est de :

- créer une interface intuitive pour permettre à l'utilisateur d'obtenir rapidement et simplement la conversion de manière relativement fiable,
- minimiser au maximum les éléments à renseigner par l'utilisateur pour obtenir sa conversion,
- optimiser le temps de chargement et de calcul de la conversion,
- proposer des données précises à l'utilisateur,
- réfléchir à un modèle économique

### 4h16 plus tard...

Il est temps pour moi de vous abandonner à ces premières fondations, en attendant le prochain épisode !

<img src="http://www.reactiongifs.com/wp-content/uploads/2013/07/exhausted.gif"/>

