---
---

### 215 jours et 8h06 plus tard...

<img src = "https://media.giphy.com/media/2rj8VysAig8QE/giphy.gif"/>

En ce moment, je travaille sur les interfaces de l’application !

Les interfaces sous Android sont essentiellement réalisées sous le format XML, le code JAVA permettant ensuite de définir la façon dont réagiront les éléments XML. Une interface est représentée dans un Layout (= vue) qui pourra à son tour contenir un ou plusieurs Layouts, dans le but d’organiser les différents éléments de l’interface et les positionner à l’intérieur de la vue. Un Layout permet par exemple de positionner les éléments dans la vue sur une ligne horizontale, ou verticale (LinearLayout), un autre permet de positionner les éléments les uns par rapport aux autres (RelativeLayout), etc.

Les éléments constituant les interfaces sont représentés par des widgets. Par exemple, une simple ligne de texte sera représentée par le widget <TextView> et un bouton par le widget Button. 

Voici par exemple une représentation XML du texte « bonjour » :

{% highlight java %}
< TextView
    android:id="@+id/texte"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:textColor="@color/black"
    android:textSize="20sp"
    android:textStyle="bold"
    android:text= "bonjour"
/>
{% endhighlight java %}

Chaque ligne contenue dans le widget Textview définie un attribut :

- android :id = définir une référence pour ce widget afin de nous permettre de l’appeler dans les différents fichiers de l’application,
- android :layout_width = déterminer la largeur de l’élément. Ici, la largeur sera celle de son élément parent, 
- android:layout_height = déterminer la hauteur de l’élément. Ici, la hauteur sera la hauteur naturelle de l’élément,
- android:textColor= définir la couleur du texte,
- android:textSize= préciser la taille du texte,
- android:textStyle= indiquer le style du texte (italique, gras, etc),
- android:text= déterminer le texte à afficher.


Voilà pour la partie théorique ! Dans la pratique, c’est…

<img src = "https://media.giphy.com/media/Z7YWBq9QCLnB6/giphy.gif"/>

Par défaut, certains widgets ne s’affichent pas toujours de la façon dont nous l’aurions imaginé. Il est nécessaire alors d’agir sur les attributs afin d’obtenir le résultat escompté.  

Voici par exemple la façon dont s’affiche une des interfaces de l’application.

<img src="/img/prev1.jpg"/>

A première vue, les éléments se positionnent correctement les uns par rapport aux autres. Pourtant, j’ai passé plusieurs heures sur cette interface qui semble terminée ! Plusieurs heures pour quoi ? Pour un simple… curseur !

J’ai inséré deux widgets <EditText> dans l’interface afin de permettre à l’utilisateur de saisir ses cotisations prévoyance (part salariale & part patronale). Jusqu’ici tout va bien, sauf qu’à l’ouverture de l’interface, c’est le curseur du second EditText qui s’affiche (part patronale), au lieu du premier (part salariale), ce qui apparaîtrait plus logique.

J’ai cherché alors parmi tous les attributs du widget comment positionner correctement mon curseur. Dans Android Studio, il est possible de faire apparaître l’ensemble des attributs disponibles d’un widget par un simple raccourci clavier (ctrl + space). L’inconvénient, c’est que seuls les noms de ces attributs apparaissent, sans leurs définitions. Pour obtenir les définitions, il faut se rendre sur la documentation Android, disponible en ligne (lien).

Dans la documentation, il est indiqué que le widget EditText hérite des attributs du widget TextView et du widget View. On retrouve alors l’ensemble des attributs, mais cette fois, avec leurs définitions.

Pour mon problème de curseur, je me suis alors intéressée de plus près aux attributs de « focus ». Mais après quelques tests sans succès, et une documentation plus approfondie du sujet, j’ai finalement découvert que les attributs « focus » géraient le positionnement du curseur, en fonction du texte saisi, et la navigation entre les différents EditText, mais pas le positionnement de départ, à l’affichage de l’interface.

<img src="https://media.giphy.com/media/TRFSdeDalM46I/giphy.gif"/>

Mais heureusement, quand la documentation ne suffit pas à nous sortir de l’impasse, il existe l’arme absolue : <a href="https://stackoverflow.com/">stackoverflow.com</a> !

Stack Overflow est un site web qui se présente sous la forme d’un forum de questions réponses liées à la programmation informatique, avec une base immense de thèmes abordés. Selon wikipedia, le site revendiquait pas moins de 10 000 000 de questions en 2015, posées par des programmateurs, aussi bien débutants qu’experts.

Le site s’adressant à de multiples utilisateurs à travers le globe, la seule langue autorisée, ou du moins fortement recommandée, est bien sûr l’anglais. Mais qui dit programmation dit documentation essentiellement disponible en anglais, alors on se fait à l’utilisation de la langue dite universelle, à tel point que pour tout ce qui touche à la programmation, j’effectue désormais l’ensemble de mes recherches de documentation en anglais.

Après quelques recherches m’orientant sur de fausses pistes, des tests infructueux, des heures de tentatives acharnées, j’ai enfin trouvé les mots clés de recherche Google qui allaient me sauver la mise : « android cursor between two edittext ». Un petit lien Stack Overflow plus loin, me voici enfin avec la solution : une simple balise complémentaire  <requestFocus/> à l’intérieur de la balise du widget, au sein de mon fichier xml, et le tour est joué !!!

<img src="/img/prev1.jpg"/>

<img src="https://media.giphy.com/media/9nCW9iugMDG4o/giphy.gif"/>

Toute cette démonstration pour simplement vous informer que j’ai planifié de proposer une première bêta de l’application avant octobre. Mais comme vous l’aurez compris, je ne suis pas à l’abri d’un widget récalcitrant, d’une problématique inattendue, ou encore d’un crash du site Stack Overflow ! Alors la bêta sera peut être disponible bien après octobre, mais aussi peut être bien avant (un miracle, qui sait…).

En attendant, je vous annonce que l’application a désormais un nom officiel et un logo ! (dont je garderai le secret jusqu’à la première bêta)

<img src="https://media.giphy.com/media/l3q2U4wz2o3Nvrr7G/giphy.gif"/>

A bientôt !
