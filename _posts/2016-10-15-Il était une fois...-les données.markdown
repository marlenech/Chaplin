
### 5 jours et 12h13 plus tard...

Les bases de tout bulletin de salaire, ce sont les données. Ces données, ça va être bien sûr le salaire brut mais aussi tous les taux de cotisations et les éléments à prendre en compte pour mes formules de calculs. Ainsi, je vais avoir par exemple à prendre en considération le plafond de la sécurité sociale, nécessaire pour déterminer à quel moment je dépasserai les cotisations appelées sur la première tranche, les taux de cotisations maladies, vieillesse, allocations familiales, la CSG/CRDS, la retraite et prévoyance, etc. Il faudra également que j'adapte ces taux selon qu'ils soient salariales ou patronales, mais aussi en fonction des statuts cadres et non-cadres.

Au boulot, les données générales au sein de notre logiciel paie sont renseignées ainsi :

<img src="/img/image.png"/>

Chaque famille de données est renseignée dans des onglets différents, avec pour certaines d'entre  elles, la différenciation entre le taux salarial et le taux patronal. 

Allez je me lance, je créé mon projet sous Android Studio. Enfin... la création d'un projet sous Android Studio demande souvent en amont d'effectuer les mises à jour des SDK, voir du logiciel (les SDK, ou kits de développement, qui permettent d'obtenir l'ensemble des outils nécessaires au développement d'une appli, sont sans cesse mis à jour pour prendre en compte les dernières fonctionnalités et dernières versions d'Android). Et là... et là... il faut patienter... encore et encore...

<img src="http://www.reactiongifs.com/r/aawt.gif"/>

Bon, en même temps, moi j'en profite pour écrire le blog !

### 2h20 plus tard...(c'était une grosse mise à jour!)



> Le premier visuel de la base de donnée sous Android

Il existe plusieurs applications sur le store qui proposent ce type d'outils, mais la plupart fonctionnent sur la base d'un taux moyen de charges salariales et n'indiquent pas le taux de charges patronales. 

L'idée ici serait de renseigner les véritables taux et les mettre à jour via une base de données externe pour obtenir un algorithme plus fiable, en fonction de la situation du salarié, voir de son secteur d'activité.

> Le Fondement : 

Pour mener à bien le projet, il me faudra réaliser une première application, qui sera plutôt perso, pour me permettre de mettre à jour facilement la base de données contenant l'ensemble des taux et autres éléments. Je pourrais tout à fait ne pas passer par une appli et me contenter d'une page web, mais comme c'est un projet Android, autant rester sous Android jusqu'au bout. 

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
