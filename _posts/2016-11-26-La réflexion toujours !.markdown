### 50 jours et 10h34 plus tard...

Cette semaine au boulot, j’ai suivi une petite formation sur le <a href="http://www.preventionpenibilite.fr/sites/preventionpenibilite/home.html">compte pénibilité</a>. La pénibilité, pour résumer rapidement, c’est l’attribution pour les salariés dépassant certains <span class="highlight-span">seuils d’expositions</span> au travail, définis strictement par la loi, de points supplémentaires pour leur retraite, utilisables également pour de la formation.

Je vous épargne le détail de l’ensemble des déclarations obligatoires liées à ce compte, qui incombent encore une fois à l’employeur. Mais la pénibilité, c’est également un nouveau taux de cotisation qui entre en vigueur au 1er janvier 2017, de <span class="highlight-span">0,01%</span> de la masse salariale pour l’ensemble des employeurs. S’ajoutent à ce taux des taux additionnels sur les rémunérations des salariés dépassant les seuils de pénibilité avec un effet rétroactif au 1er janvier 2015.

<img src = "http://www.reactiongifs.com/r/whid.gif"/>

Passé le moment de longue déprime entre collègues face à une nouvelle mission administrative, parmi quelques autres toutes récentes (si je prononce DSN, certains sauront de quoi je parle), qui viennent malheureusement de plus en plus ternir la richesse de notre métier, j’ai pensé projet ! Mon projet ! 

A ce jour, ma base de données comporte l’ensemble des taux actuellement en vigueur. Mais qu’en est-il des <span class="highlight-span">nouveaux taux</span> ? Ces cotisations qui n’existent pas à ce jour et qui fleurissent rarement au printemps mais plutôt en début d’année ? Je n’ai pas prévu ce cas de figure dans mon appli…

J’ai alors réfléchi un moment à une solution : insérer un bouton sur chaque interface pour ajouter une cotisation, qui viendra alors s’ajouter dans ma base de données, mais aussi sur mon interface… Oui mais ce taux ne sera pas ajouté dans mon appli de conversion… ou alors il faut prendre en compte la possibilité de l’ajout d’un nouveau taux dans l’algorithme de conversion… oui mais comment faire s’il s’agit d’un allègement (oui oui, c’est possible parfois) plutôt que d’un taux de cotisation complémentaire ?

<img src = "http://www.laboiteverte.fr/wp-content/uploads/2011/09/12-Casino.gif"/>

Finalement… je ne vais pas prendre en compte cette hypothèse. Comme je le disais plus haut, les nouvelles cotisations sont généralement mises en vigueur en début d’année. Et puis, ce n’est pas si régulier. Cette année par exemple, il n’y a, à ma connaissance, qu’une seule cotisation dont le calcul a sensiblement été modifié en cours d’année : la <span class="highlight-span">cotisation allocation familiale complémentaire</span>. Aussi, il me suffira de mettre à jour mon application de gestion de la base de données et mon algorithme de calcul dans l’application de conversion pour prendre en compte ce genre de cas de figure. 

Voilà, tout cela pour démontrer que réaliser un projet de programmation, c’est constamment le <span class="highlight-span">remettre en question</span>, penser <span class="highlight-span">optimisation</span>, et avoir conscience qu’il faudra régulièrement <span class="highlight-span">s’adapter aux nouvelles situations</span> et cas de figure auxquels nous n’avons pas pensé en débutant le projet. 

Mais évidemment, je ne vais pas finaliser cet article sans vous donner des nouvelles de mes avancements ! Aujourd’hui, j’ai quasiment terminé mon application de gestion de la base de données, hormis bien sûr l’ajout des différents cas de figure auxquels je n’ai pas pensé à ce jour. Il me reste deux-trois interfaces à créer avant d’avoir réellement toutes les données de base nécessaires au calcul de conversion. Mais comme c’est un travail un peu répétitif (créer les données dans la base, créer chaque view dans l’appli, attribuer une variable à chaque donnée de la base, afficher chaque donnée dans les views correspondantes grâce à chaque variable), pour varier les plaisirs, j’ai commencé à travailler sur l’application de conversion et notamment sur la présentation de l’interface. Je rédigerai un article tout particulièrement consacré au sujet, mais en attendant voici un petit aperçu de la première version :

<img src = "https://marlenech.github.io/img/nov.-25-2016%2022-57-31.gif"/>

A bientôt !

