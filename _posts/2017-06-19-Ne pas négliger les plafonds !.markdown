### 193 jours et 0h28 plus tard...

Pas d’inquiétude ! Je ne vais pas vous faire un tuto sur comment réussir la peinture de vos plafonds. Non, quand je parle de plafonds, ce sont les plafonds de la sécurité sociale...

<img src = "https://media.giphy.com/media/sA8HUiA09PWtq/giphy.gif"/>

Non ! Ne partez pas ! En matière de technique de paie, le plafond de la sécurité sociale (=PSS) est une donnée essentielle, c’est grâce à son montant que nous allons pouvoir déterminer le passage des différentes tranches de salaire et appliquer correctement les taux de cotisations en vigueur pour chaque tranche. Certaines bases de cotisations sont également parfois plafonnées au montant du PSS.

Bon jusque là, rien de bien compliqué pour une intégration du PSS dans mon projet d’application. J’indique le montant du PSS mensuel dans ma base de données et récupère celui-ci à chaque conversion pour appliquer correctement les taux de cotisations en fonction du salaire brut saisi, selon qu’il soit inférieur ou supérieur au PSS.

<img src = "https://media.giphy.com/media/zcCGBRQshGdt6/giphy.gif"/>

Mais cette méthode ne serait adaptée que dans le cas d’un salaire mensuel à temps plein. Or, dans l’application, je laisse le choix à l’utilisateur de convertir un salaire journalier, mensuel ou annuel. Il faut donc que je traite le plafond aussi bien journalier, mensuel qu’annuel. De plus, l’utilisateur doit pouvoir saisir un nombre d’heures lié au salaire renseigné si celui-ci ne correspond pas à un temps plein. Dans ce cas, il faut alors proratiser le plafond.


<img src = "https://media.giphy.com/media/11VFoOchZjsvn2/giphy.gif"/>

Donc pour vous donner un exemple, pour calculer les cotisations Retraite pour un non-cadre, voici comment je procède :

-	Je récupère le salaire brut saisi par l’utilisateur,
-	Je récupère le contenu de la coche que l’utilisateur a sélectionné pour le type de salaire saisi « journalier », « mensuel » ou « annuel »,
-	Je détermine le plafond selon que le salaire soit journalier, mensuel ou annuel
-	Je récupère le nombre d’heures saisi par l’utilisateur si le salaire renseigné ne correspond pas à un temps plein,
-	Je détermine à nouveau le plafond dans le cas où le salaire soit équivalent à un temps partiel,
-	J’appelle via ma base de données les taux de cotisations Retraite Tranche A et B, ainsi que l’AGFF Tranche A et B,
-	J’applique ces taux au salaire saisi par l’utilisateur et/ou au PSS déterminé précedemment.

Voici comment ces étapes se présentent au sein de mon code :

Ma méthode PlafondType() récupère le type de salaire selectionné par l’utilisateur :

```java
//Plafond : détermination selon le type de salaire saisi


public Float PlafondType() {

float plafondType;

    switch (plafond) {
        case 0: //Si le type de salaire est journalier
            plafondType = PlafondSSJ(); //=Plafond journalier
            break;
        case 1: //Si le type de salaire est mensuel
            plafondType = PlafondSS(); //=Plafond mensuel
            break;
        case 2: //Si le type de salaire est annuel
            plafondType = PlafondSSA(); //=Plafond annuel
            break;
    }

    return plafondType;
}
```

Ensuite la méthode PlafondHoraire() récupère le résultat de PlafondType() et le proratise par le nombre d’heures (=horaire) saisi par l’utilisateur si le nombre d’heures est inférieur à un temps plein (=TempsPleinRef()) :

```java
public Float PlafondHoraire() {

    float plafondHoraire;

    if (horaire < TempsPleinRef()) {
        plafondHoraire = (PlafondType() / TempsPleinRef()) * horaire;
    }
    else {
        plafondHoraire = PlafondType();
    }

    return plafondHoraire;
}
```

Mon plafond ainsi déterminé, je peux désormais lancer le calcul de mes cotisations retraite en fonction du plafond :

```java
//Calcul des cotisations Retraite TA Part Salariale
public Float CalculRetraiteTAPS() {

    float calRetraiteTaPs;

        if (salaire < PlafondHoraire()) {
            calRetraiteTaPs = (salaire * TotalTauxRetraiteTaPS()) / 100;
        }
        else {
            calRetraiteTaPs = (PlafondHoraire() * TotalTauxRetraiteTaPS()) / 100;
        }
    return calRetraiteTaPs;

}

//Calcul des cotisations Retraite TB Part Salariale
public Float CalculRetraiteTBPS() {

    float calRetraiteTbPs;

        if (salaire > PlafondHoraire() && salaire <= (PlafondHoraire()*3)) {

            calRetraiteTbPs = ((salaire - PlafondHoraire()) * TotalTauxRetraiteTbPS()) / 100;
        } else if (salaire > (PlafondHoraire()*3)) {

            calRetraiteTbPs = (((PlafondHoraire()*3) - PlafondHoraire()) * TotalTauxRetraiteTbPS()) / 100;
        } else
            {
                calRetraiteTbPs = 0;
            }
            
    return calRetraiteTbPs;

}

//Calcul des cotisations Retraite Totale Part Salariale
public Float CalculRetraiteTotPS() {

    float calRetraiteTotPs = CalculRetraiteTAPS() + CalculRetraiteTBPS();

    return calRetraiteTotPs;

}

```

Les méthodes TotalTauxRetraiteTaPS() et TotalTauxRetraiteTbPS() sont définies dans une autre classe et sont constituées simplement des taux appelés via ma base de données pour les cotisations de retraite complémentaire et Agff Tranche A et B.

La tranche B de la cotisation Retraite ne devant pas dépasser 3 PSS, je compare le salaire saisi par l’utilisateur avec 3 PSS, ainsi si le salaire est supérieur, j’applique les taux de cotisations de la Retraite Tranche B uniquement sur 3 plafonds et non pas le salaire total.

Voici maintenant comment ces méthodes se présentent au sein de l’application (je précise que l’interface n’est pour le moment pas du tout finalisée !!!) :

<img src = "https://marlenech.github.io/img/gif_plafond_1.gif"/>

Je saisie un salaire de 3000 € pour 151,67 heures/mensuelles (soit un temps plein). Le plafond mensuel de la sécurité sociale étant de 3269 € et donc inférieur au salaire saisi, j’y applique seulement les taux de cotisations dus sur la tranche A. Les taux de cotisations sont de 3,10% pour la Retraite complémentaire salariale Tranche A et 0,8% pour l’AGFF salariale Tranche A. Ainsi, les cotisations retraite pour un salaire mensuel de 3000 € à temps plein est de 117 €.

<img src = "https://marlenech.github.io/img/gif_plafond_2.gif"/>

Je conserve ici un salaire de 3000 € mais je modifie le nombre d’heures par 80 heures mensuelles. Le plafond mensuel de la sécurité sociale se réduit alors à 1724,27 €. Il est alors supérieur au salaire saisi. Dans ce cas, une tranche B va se déclencher. Les taux de cotisations sont de 8,10% pour la Retraite complémentaire salariale Tranche B et 0,9% pour l’AGFF salariale Tranche B. La cotisation salariale Retraite Tranche A sera alors de 67,25 € (=1724,27*3,9%) et de 114,82 € (=(3000-1724,27)*9%).

Ouf ! Il ne me reste plus maintenant qu’à créer mes méthodes pour réaliser la conversion du salaire d’un cadre et retravailler l’ensemble de mon interface pour la rendre plus harmonieuse, pour pouvoir vous proposer une première version Beta de l’appli !

<img src = "https://media.giphy.com/media/a9d3bbcM3ImXe/giphy.gif"/>

A bientôt !
