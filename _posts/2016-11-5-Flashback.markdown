### 28 jours et 05h54 plus tard...

Entre les tours gigantesques de legos, la voiture méga super cool télécommandée, les ballades en trottinette  qui va « vite vite vite maman », le week-end de pont n’a pas été réellement en faveur de l’avancé du projet. 

<img src="http://mariecha.m.a.pic.centerblog.net/epxg7u77.gif" />

Toutefois, ne pas coder m’a permis de réfléchir à des aspects plus généraux du projet. Et c’est pas plus mal, parce que j’avais omis quelques <span class="highlight-span">petites particularités</span> lorsque j’ai commencé à coder l’appli de gestion de la base de données.

Je vous explique : lorsque j’ai pensé, au départ du projet, à la structure de ma base de données, j’ai simplement imaginé une base reliant <span class="highlight-span">chaque cotisation au taux correspondant</span>, par exemple, un taux salarial à 0,75% pour la cotisation maladie, et ainsi de suite. Bref, quelque chose de très basique.

Mais en paie, il existe une notion très importante à ne pas négliger : <span class="highlight-span">la date de validité</span>. Et oui, un taux de cotisation ça change, ça augmente, ou ça diminue, et même souvent, selon les cotisations, une fois par an voir beaucoup plus fréquemment. Les taux sont révisés soit par le gouvernement, par les caisses destinataires des cotisations, par les conventions collectives, etc, qui déterminent alors une date obligatoire de prise en compte des taux révisés. Nous avons par exemple une révision avec mise en application au 1er janvier de chaque année de divers taux d’origine légale, mais aussi des plafonds de la sécurité sociale, du SMIC, etc.

Ah c’est chouette ça, vous allez me dire, je vais pouvoir « m’éclater » à modifier ma base de données à chaque révision. Oui mais moi, le <span class="highlight-span">1er janvier</span>, je ne serai sans doute pas devant mon appli à mettre à jour tous mes taux de cotisations, je serai plutôt… comme ça

<img src="http://www.reactiongifs.com/r/machine.gif"/>

voir comme ça…

<img src="http://www.reactiongifs.com/wp-content/uploads/2013/05/dead.gif"/>

Alors il a fallut que je repense la structure de ma base. Finalement, à chaque cotisation, je dois associer un taux et une date de validité. Mais je dois tout de même conserver le taux existant avant cette nouvelle date de validité, pour que ce soit celui-ci qui soit appelé avant la mise en application du nouveau taux. 

En farfouillant un peu sur le net, j’ai découvert alors qu’il était possible de gérer l’historique des entrées dans une base MYSql en utilisant simplement des requêtes sql automatiques, que l’on appelle des <span class="highlight-span"> « triggers </span>.  Cela permet par exemple d’enregistrer les anciennes données mises à jour dans une table dédiée, « historique » par exemple, et ainsi de pouvoir réutiliser cette table et ces données. J’ai alors regardé quelques tutos sur le sujet, et puis je suis tombée un peu par hasard sur LA mauvaise nouvelle : les triggers ne sont pas accessibles via une base de données rattachée à un <span class="highlight-span">hébergement mutualisé chez OVH</span>. Pas de chance, je suis justement en hébergement mutualisé chez OVH ! Après confirmation par leur service technique, ils m’ont redirigé vers une base de données dédiée, en hébergement pro. Il  faut compter minimum 6 € par mois (HT) pour une telle base.

Bon, moi comme j’ai encore du travail sur mon projet, et que je n’ai aucune idée du succès que pourrais avoir mon appli, je me suis fixée comme ligne de conduite de <span class="highlight-span">dépenser le strict minimum</span> pour la réalisation du projet. 

J’ai donc finalement simplement revu la structure de ma base et oublié, pour le moment, les triggers. Dans ma table, j’aurai donc <span class="highlight-span">la cotisation + le nouveau taux + l’ancien taux + la date de validité </span>. Ainsi, dans mon code, il me suffira de dire que lorsque la date de validité est supérieure à la date du jour, le calcul doit se faire à partir de l’ancien taux, sinon il faut prendre le nouveau. 

Mais cette réflexion m’amène à devoir également réécrire mon code en fonction de cette nouvelle donne. Parce que, après mon dernier article, j’avais enfin réussi à afficher les données de la base dans mon appli et à les mettre à jour… et là il faut tout revoir !

<img src= "http://www.reactiongifs.com/r/com.gif " />

> Pour la petite histoire (voir mon précédant article <a href=" https://marlenech.github.io/2016/Les-probl%C3%A8mes-commencent.html" >ici</a>), mon code initial ne fonctionnait pas en raison d’un « s » oublié, oui oui !

A très vite pour la suite !
