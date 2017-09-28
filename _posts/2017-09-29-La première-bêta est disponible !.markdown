---
---
### 300 jours et 2h46 plus tard...


Ouf ! Ça y est ! Après une multitude de tests, de résolutions de crash, de <a href="https://stackoverflow.com/questions/218384/what-is-a-nullpointerexception-and-how-do-i-fix-it" >NullPointerException</a>, j’ai enfin publié une première Bêta de l’appli !

<img src = "https://media.giphy.com/media/l3V0wkQ2KKcAeW8Cs/giphy.gif"/>

Mais qu’est ce qu’une <span class="highlight-span">Bêta</span> ? Dans le développement d’une application, il est préférable et même, vivement conseillé, de passer d’abord par des versions de tests avant une publication de l’application finalisée.

Ainsi, la publication d’une application possède deux phases de tests possibles : <span class="highlight-span">Alpha</span> et <span class="highlight-span">Bêta</span> (qui peuvent chacune contenir plusieurs versions) et une phase de <span class="highlight-span">Production</span> (release), soit de publication de l’application finalisée.

Les versions Alpha sont généralement moins avancées que les versions Bêta. Il s’agit par exemple de tester une fonctionnalité particulière de l’application. La version Bêta, quant à elle, se rapproche plus de la version finalisée de l’application.

Le but de ces versions tests est de rendre l’application disponible à un <span class="highlight-span">panel d’utilisateurs</span>, soit de manière fermée (avec invitation personnel à un petit nombre d’utilisateurs), soit de manière ouverte.

Pour mon application, je ne suis pas passée par une phase de test Alpha pour le moment, n’ayant pas réellement de fonctionnalités isolées à tester. L’objet de l’application, soit la conversion d’un salaire, nécessitant une version plutôt aboutie de l’application pour fonctionner, une première version Bêta était alors davantage justifiée.

Le but est alors, avec cette version Bêta, de permettre à une multitude d’utilisateurs de tester cette première version et de détecter alors d’éventuels <span class="highlight-span">bugs ou crash</span> avant la publication de la version finalisée. J’ai choisi alors d’ouvrir cette phase de test, les tests fermés étant généralement utilisés au sein d’une équipe de développeur ou au sein d’une entreprise.

<img src = "https://media.giphy.com/media/NWg7M1VlT101W/giphy.gif"/>

Concernant le contenu de l’appli, cette première version permet une <span class="highlight-span">conversion d’un salaire brut en net</span>, de manière plutôt précise, en proposant à l’utilisateur de saisir ses taux de prévoyance, mutuelle et retraite supplémentaire, ces trois éléments étant essentiels à l’obtention d’un résultat au plus juste.

Aussi, voici les éléments pris en compte dans le calcul de la conversion pour cette première version de test :

-	Catégories : non cadre, cadre, gérant,
-	Temps de travail : temps partiel, temps plein, forfait jour,
-	Salaire brut journalier, mensuel ou annuel,
-	Plafond de la sécurité sociale en fonction de temps de travail et de la périodicité du salaire,
-	Parts salariales et patronales de prévoyance, mutuelle et retraite supplémentaire,
-	Réintégrations sociales et fiscales des parts salariales et patronales de prévoyance, mutuelle et retraite supplémentaire,
-	Base assujettie à la CSG/CRDS et plafonnement de l’abattement,
-	Net imposable.

<img src = "https://media.giphy.com/media/AXorq76Tg3Vte/giphy.gif"/>

Voilà, il ne me reste plus qu’à vous laisser tester l’appli tranquillement, en suivant le lien ci-dessous : 

<a href="https://play.google.com/apps/testing/brutanet.salaire.italikdesign.com.brutanet">VERSION BETA ICI</a>

N’hésitez pas à tester tous les boutons de l’appli, à vérifier la précision du calcul de conversion avec votre propre bulletin de salaire, et puis à en parler autour de vous, à inviter votre entourage à tester l’appli, etc.

A bientôt !
