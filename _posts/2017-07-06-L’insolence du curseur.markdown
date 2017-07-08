<!-- META FACEBOOK -->
<meta property="og:description" content="215 jours et 8h06 plus tard...
En ce moment, je travaille sur les interfaces de l’application !

Les interfaces sous Android sont essentiellement réalisées sous le format XML, le code JAVA permettant ensuite de définir la façon dont réagiront les éléments XML. Une interface est représentée dans un Layout (= vue) qui pourra à son tour contenir un ou plusieurs Layouts, dans le but d’organiser les différents éléments de l’interface et les positionner à l’intérieur de la vue. Un Layout permet par exemple de positionner les éléments dans la vue sur une ligne horizontale, ou verticale (LinearLayout), un autre permet de positionner les éléments les uns par rapport aux autres (RelativeLayout), etc." />
---
---

### 215 jours et 8h06 plus tard...

<img src = "https://media.giphy.com/media/2rj8VysAig8QE/giphy.gif"/>

En ce moment, je travaille sur les <span class="highlight-span">interfaces</span> de l’application !

Les interfaces sous Android sont essentiellement réalisées sous le format <span class="highlight-span">XML</span>, le code JAVA permettant ensuite de définir la façon dont réagiront les éléments XML. Une interface est représentée dans un <span class="highlight-span">Layout</span> (= vue) qui pourra à son tour contenir un ou plusieurs Layouts, dans le but d’organiser les différents éléments de l’interface et les positionner à l’intérieur de la vue. Un Layout permet par exemple de positionner les éléments dans la vue sur une ligne horizontale, ou verticale (LinearLayout), un autre permet de positionner les éléments les uns par rapport aux autres (RelativeLayout), etc.

Les éléments constituant les interfaces sont représentés par des <span class="highlight-span">widgets</span>. Par exemple, une simple ligne de texte sera représentée par le widget <span class="highlight-span">TextView</span> et un bouton par le widget <span class="highlight-span">Button</span>. 

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

Chaque ligne contenue dans le widget Textview définit un <span class="highlight-span">attribut</span> :

- <span class="highlight-span">android :id</span> = définir une référence pour ce widget afin de nous permettre de l’appeler dans les différents fichiers de l’application,

- <span class="highlight-span">android :layout_width</span> = déterminer la largeur de l’élément. Ici, la largeur sera celle de son élément parent, 

- <span class="highlight-span">android:layout_height</span> = déterminer la hauteur de l’élément. Ici, la hauteur sera la hauteur naturelle de l’élément,

- <span class="highlight-span">android:textColor</span> = définir la couleur du texte,

- <span class="highlight-span">android:textSize</span> = préciser la taille du texte,

- <span class="highlight-span">android:textStyle</span> = indiquer le style du texte (italique, gras, etc),

- <span class="highlight-span">android:text</span> = déterminer le texte à afficher.


Voilà pour la partie théorique ! Dans la pratique, c’est…

<img src = "https://media.giphy.com/media/Z7YWBq9QCLnB6/giphy.gif"/>

Par défaut, certains widgets ne s’affichent pas toujours de la façon dont nous l’aurions imaginé. Il est nécessaire alors d’agir sur les attributs afin d’obtenir le résultat escompté.  

Voici par exemple la façon dont s’affiche une des interfaces de l’application.

<img src="/img/prev2.png"/>

A première vue, les éléments se positionnent correctement les uns par rapport aux autres. Pourtant, j’ai passé plusieurs heures sur cette interface qui semble terminée ! Plusieurs heures pour quoi ? Pour un simple… <span class="highlight-span">curseur</span> !

J’ai inséré deux widgets <span class="highlight-span">EditText</span> dans l’interface afin de permettre à l’utilisateur de saisir ses <span class="highlight-span">cotisations prévoyance</span> (part salariale & part patronale). Jusqu’ici tout va bien, sauf qu’à l’ouverture de l’interface, c’est le curseur du second EditText qui s’affiche (part patronale), au lieu du premier (part salariale), ce qui apparaîtrait plus logique.

J’ai cherché alors parmi tous les attributs du widget comment positionner correctement mon curseur. Dans <span class="highlight-span">Android Studio</span>, il est possible de faire apparaître l’ensemble des attributs disponibles d’un widget par un simple raccourci clavier (ctrl + space). L’inconvénient, c’est que seuls les noms de ces attributs apparaissent, sans leurs définitions. Pour obtenir les définitions, il faut se rendre sur la <span class="highlight-span">documentation Android</span>, disponible <a href="https://developer.android.com/reference/android/widget/EditText.html" >en ligne</a>.

Dans la documentation, il est indiqué que le widget EditText hérite des attributs du widget <span class="highlight-span">TextView</span> et du widget <span class="highlight-span">View</span>. On retrouve alors l’ensemble des attributs, mais cette fois, avec leurs définitions.

Pour mon problème de curseur, je me suis alors intéressée de plus près aux attributs <span class="highlight-span">focus</span>. Mais après quelques tests sans succès, et une documentation plus approfondie du sujet, j’ai finalement découvert que les attributs « focus » géraient le positionnement du curseur, en fonction du texte saisi, et la navigation entre les différents EditText, mais pas le positionnement de départ, à l’affichage de l’interface.

<img src="https://media.giphy.com/media/TRFSdeDalM46I/giphy.gif"/>

Mais heureusement, quand la documentation ne suffit pas à nous sortir de l’impasse, il existe l’arme absolue : <a href="https://stackoverflow.com/">stackoverflow.com</a> !

Stack Overflow est un site web qui se présente sous la forme d’un forum de <span class="highlight-span">questions réponses</span> liées à la programmation informatique, avec une base immense de thèmes abordés. Selon wikipedia, le site revendiquait pas moins de 10 000 000 de questions en 2015, posées par des programmateurs, aussi bien débutants qu’experts.

Le site s’adressant à de multiples utilisateurs à travers le globe, la seule langue autorisée, ou du moins fortement recommandée, est bien sûr <span class="highlight-span">l’anglais</span>. Mais qui dit programmation dit documentation essentiellement disponible en anglais, alors on se fait très vite à l’utilisation de la langue dite universelle, à tel point que pour tout ce qui touche à la programmation, j’effectue désormais l’ensemble de mes recherches de documentation en anglais.

Après quelques recherches m’orientant sur de fausses pistes, des tests infructueux, des heures de tentatives acharnées, et un petit lien <a href="https://stackoverflow.com/questions/11226710/how-to-place-cursor-to-certain-edittext-box" >Stack Overflow</a> plus tard, me voici enfin avec la solution : une simple balise complémentaire <span class="highlight-span">requestFocus</span> à l’intérieur de la balise du widget, au sein de mon fichier xml, et le tour est joué !!!

<img src="/img/prev1.png"/>

<img src="https://media.giphy.com/media/9nCW9iugMDG4o/giphy.gif"/>

Cette petite démonstration pour simplement vous informer que j'envisage de proposer une première bêta de l’application <span class="highlight-span">avant octobre</span>. Mais comme vous l’aurez compris, je ne suis pas à l’abri d’un widget récalcitrant, d’une problématique inattendue, ou encore d’un crash du site Stack Overflow ! Alors la bêta sera peut être disponible bien après octobre, mais aussi peut être bien avant (un miracle, qui sait…).

En attendant, je vous annonce que l’application a désormais un nom officiel et un logo ! (dont je garderai le secret jusqu’à la première bêta)

<img src="https://media.giphy.com/media/l3q2U4wz2o3Nvrr7G/giphy.gif"/>

A bientôt !
