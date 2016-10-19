
### 5 jours et 12h13 plus tard...

Les bases de tout bulletin de salaire, ce sont les données. Ces données, ça va être bien sûr le salaire brut mais aussi tous les taux de cotisations et les éléments à prendre en compte pour mes formules de calculs. Ainsi, je vais avoir par exemple à prendre en considération le plafond de la sécurité sociale, nécessaire pour déterminer à quel moment je dépasserai les cotisations appelées sur la première tranche, les taux de cotisations maladies, vieillesse, allocations familiales, la CSG/CRDS, la retraite et prévoyance, etc. Il faudra également que j'adapte ces taux selon qu'ils soient salariales ou patronales, mais aussi en fonction des statuts cadres et non-cadres.

Au cabinet dans lequel je travaille, les données générales au sein de notre logiciel paie se présentent ainsi :

<img src="/img/image.png"/>

Chaque famille de données est renseignée dans des onglets différents, avec pour certaines d'entre  elles, la différenciation entre le taux salarial et le taux patronal. Ces données vont ensuite être intégrées dans les bulletins de salaire et/ou dans les formules de calcul nécessaires à l'établissement des bulletins. Viennent s'ajouter également les données liées aux conventions collectives, aux fiches salariés, etc.

Ainsi, il va me falloir dans mon appli intégrer la plupart de ces informations pour obtenir par la suite une conversion fiable d'un salaire brut à un salaire net.

Allez je me lance, je créé mon appli de gestion de ma base de données sous Android Studio. Enfin... la création d'un projet sous Android Studio demande souvent en amont d'effectuer les mises à jour des SDK, voir du logiciel (les SDK, ou kits de développement, qui permettent d'obtenir l'ensemble des outils nécessaires au développement d'une appli, sont sans cesse mis à jour pour prendre en compte les dernières fonctionnalités et dernières versions d'Android). Et là... et là... il faut patienter... encore et encore...

<img src="http://www.reactiongifs.com/r/aawt.gif"/>

Bon, en même temps, moi j'en profite pour écrire le blog !

> Petite parenthèse : Android Studio, c'est le logiciel préconisé par Google pour le développement d'applications Android. Il est disponible gratuitement <a href="https://developer.android.com/studio/index.html">ici</a>.

### et 2h20 plus tard...(c'était une grosse mise à jour!) 

Sous Android, on appelle les différentes fenêtres qui s'affichent à l'écran des "vues". Pour réaliser une vue, ça se passe un peu comme ça :

<img src="http://i.imgur.com/3nWzyYX.gif"/>

Il est nécessaire de définir des attributs pour chaque élément (widgets) de la vue (text, editText, button, etc) et les placer en fonction de l'écran, puis des éléments "parents" mais également des widgets entre eux.

Heureusement plusieurs types de "layout" (type de mise en page) existent pour faciliter <s>légèrement</s> la création des vues. Je me suis alors basée sur une mise en page de type tableau : le gridlayout. Il permet alors de positionner les éléments à la manière d'une insertion dans un tableau.

> Le premier visuel de l'appli qui va gérer la base de donnée sous Android

Après avoir créé un petit logo pour l'appli, j'ai réalisé un premier visuel de l'interface de l'appli. Voici une capture d'écran de l'interface "URSSAF" :

<img src="/img/screenshot1.png"/>

Le code source de l'interface est disponible <a href="https://github.com/marlenech/BddPaye/blob/master/app/src/main/res/layout/fragment_urssaf.xml">ici</a>.

Et voici le menu principal de l'appli :

<img src="/img/Screenshot_1476866716.png"/>

Voilà, maintenant que j'ai construit au moins une interface, il va me falloir réfléchir à ce que je vais utiliser comme méthode d'échange des données (fournisseur de contenu, web, base de données sql, etc) et la tester sur cette première interface avant de continuer la réalisation de l'ensemble des interfaces.

Mais avant tout, nous sommes mercredi, la journée des enfants, et c'est le réveil de mon petit ogre de 2 ans alors si je n'y vais pas tout de suite, je vais finir comme ça :

<img src="http://maguy69.m.a.pic.centerblog.net/e6f84f86.gif"/>

A bientôt !


