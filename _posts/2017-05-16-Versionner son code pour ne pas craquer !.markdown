### 158 jours et 5h36 plus tard...

Cette semaine, j’ai testé différents codes, différentes façon d’organiser mes fichiers, renommé mes variables une quinzaine de fois, ajouté des données, créé et supprimé des fichiers, etc. L’application a connu alors une dizaine de versions différentes en seulement sept jours.

Lorsque j’ai commencé la programmation, quand j’étais encore jeune, c’est à dire hier… avant hier… enfin bref (je vais changer de sujet), lorsqu’une version de mon programme était fonctionnelle, je la sauvegardais dans un dossier à part et je continuais le développement sur le programme initial. Ainsi, j’avais la possibilité de reprendre le développement à partir de la version sauvegardée au cas où le développement d’une nouvelle fonctionnalité sur le programme initial n’était pas probant. Et je procédais ainsi pour chaque fonctionnalité avec autant de sauvegardes que de fonctionnalités réussies.

<img src = "https://media.giphy.com/media/50UZqs7HoH6GQ/giphy.gif"/>

Bon, je ne vous cache pas que cette méthode a vite montré ses limites, à tel point que je me retrouvais parfois  à développer des fonctionnalités sur des versions qui finalement n’étaient pas abouties, ne me rappelant plus où j’avais sauvegardé la dernière version fonctionnelle, à devoir réécrire des parties de codes supprimées par inadvertance…

<img src = "https://media.giphy.com/media/14rFOnuCm4yxzi/giphy.gif"/>

Mais un jour, au détour d’un tuto, j’ai entendu parler de versioning. 

<img src = "https://media.giphy.com/media/3NtY188QaxDdC/giphy.gif"/>

Le versioning, ou gestionnaire de version est simplement un outil qui permet de conserver les différentes étapes d’un projet, de consulter les modifications entre chaque version et avec l’avantage de pouvoir revenir à une version antérieure. Le plus connu est sans doute <a href="https://fr.wikipedia.org/wiki/Git">Git</a>. Git est un logiciel de version, qui fonctionne sous forme de lignes de commandes afin de commenter et conserver les différentes versions d’un projet.

Et pour faciliter davantage le versioning, des services en ligne d’hébergement et de gestion de versions de code sont disponibles. J’ai par exemple hébergé une partie de mon code et mes différentes versions de l’application me permettant de gérer la base de données des cotisations servant au calcul de mon appli de conversion sous <a href="https://github.com/marlenech/BddPaye">Github</a>. L’avantage de Github est qu’il est orienté réseaux sociaux et open-source, de sorte que  chaque utilisateur peut contribuer aux codes disponibles en open-source. Il héberge une multitude de codes sources consultables gratuitement.

Pour le code source de mon projet de convertisseur, je n’ai pas souhaité le rendre accessible en open-source. En effet, c’est un projet qui associe le développement à une technicité, le calcul d’un salaire. Si ce code était réutilisé sans connaissance préalable de la gestion de paie, ceci pourrait induire en erreur les éventuels utilisateurs du programme ainsi proposé, et en ferait alors un outil plutôt dangereux, le but du code étant notamment d’accompagner un employeur sur la détermination du salaire de son futur salarié.

Github propose des hébergements privés pour versionner un projet sans que celui-ci soit accessible au public, mais ces hébergements sont payants. Heureusement, il existe d’autres services en ligne comme <a href"https://bitbucket.org/">Bitbucket</a>. Le site fonctionne de manière assez similaire que Github, mais l’hébergement privé y est gratuit (mais avec un nombre de contributeur limité sur un même projet). C’est donc sous Bitbucket que je versionne et sauvegarde mon appli de conversion.

Une petite démonstration :

Après avoir modifié le temps d’attente entre deux animations dans une de mes vues, j’ai lancé le terminal d’Android Studio afin de saisir mes commandes Git (A noter que je suis pas défaut en lien avec le serveur distant, hébergé par Bitbucket). J’ai commencé par un ‘git  commit –am’’temps à 1000’’ : je valide ma modification par l’expression « commit », indexe le fichier dans Git par « -a », et ajoute le message correspondant à ma modification par « -m » (les commandes –a et –m peuvent être rattachées pour gagner du temps). Enfin, j’ai lancé la commande « git push origin demo » qui m ‘a permis alors de « pousser » ma modification sur le serveur distant.

Je précise que, dans le cadre du développement de mon projet, je travaille sous deux branches : master et dev. Je développe et teste mes fonctionnalités sous la branche dev, et lorsque l’appli est opérationnelle, je pousse ces nouvelles fonctionnalités sur la branche master (= la branche fonctionnelle). J’ai créé en complément la branche demo simplement pour vous faire partager cette petite démonstration.

Voici alors comment se présente cette modification dans Bitbucket.

J’ai ainsi accès de manière très aisé à l’ensemble des modifications que j’ai pu effectuer dans mon code, et je peux très facilement revenir sur des versions antérieures de l’appli. Si vous souhaitez en savoir plus sur l’environnement Git et l’ensemble de ses commandes et fonctionnalités, voici le <a href="https://git-scm.com/book/fr/v2">lien de la documentation en français</a>.

Voilà, tout ça pour vous dire que pour moi, Git c’est un peu comme…

<img src = "https://media.giphy.com/media/VvxtXb86Lwicw/giphy.gif"/>

Sinon, côté projet, j’ai plutôt bien avancé ces derniers jours. J’ai finalisé mon architecture, rapatrié l’ensemble de mes données, notamment les taux de cotisations enregistrés sous ma base de données Sql en ligne, au sein de l’application et je suis en train d’élaborer les différents algorithmes nécessaires à l’obtention des résultats de conversion. J’espère pouvoir vous préparer une petite démonstration rapidement.

<img src = "https://media.giphy.com/media/R8MIGe47XWx68/giphy.gif"/>

A bientôt !
