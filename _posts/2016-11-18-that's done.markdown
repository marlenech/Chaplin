### 42 jours et 07h18 plus tard...

Ma conclusion pour ces deux dernières semaines : <span class="highlight-span">le projet avance</span> ! 

<img src = "http://www.reactiongifs.com/wp-content/uploads/2014/01/yippie.gif"/>

Et oui, j’ai bien avancé sur le développement de mon appli perso qui me servira à mettre à jour ma base de données contenant les taux de cotisations et autres, nécessaire pour l’appli publique qui, elle, <span class="highlight-span">convertira un salaire brut en net</span>. J’ai finalisé la partie technique pour permettre l’affichage des taux, la mise à jour de ceux-ci, tout en prenant en compte la notion de « <span class="highlight-span">date de validité</span> » (voir mon <a href=" https://marlenech.github.io/2016/Flashback.html">précédent post</a>).


<img src = "https://marlenech.github.io/img/nov.-18-2016%2023-05-05.gif"/>

Un simple click sur mes « TextView » (= les taux de cotisations) me permet d’accéder à une nouvelle fenêtre dans laquelle je peux mettre à jour les données. Elles vont alors automatiquement s’enregistrer dans ma <span class="highlight-span">base de données mySQL</span>.

L’application compare également la date du jour avec la date de validité de chaque donnée afin d’afficher <span class="highlight-span">la valeur en vigueur au moment de l’affichage</span>.


<img src = "https://marlenech.github.io/img/nov.-18-2016%2021-49-31.gif"/>

Ici, je modifie mon nouveau taux (qui est celui qui s’affiche par défaut) avec une date de validité au 01/12/2016. La date du jour étant le 18/11/2016, l’application va alors afficher l’<span class="highlight-span">ancien taux</span> enregistré.

<img src=" http://www.reactiongifs.com/wp-content/uploads/2013/06/fart-in-elevator.gif"/>

Il me reste tout de même maintenant à enregistrer l’ensemble de mes données pour les afficher dans l’application, car seule la view « Urssaf » est disponible pour le moment. 

Après cela, nous pourrons alors entrer dans le vif du sujet : <span class="highlight-span">l’application publique et le calcul d’une paie</span> !

En attendant, je vous rappelle que l’ensemble du code source est disponible sur <a href=" https://github.com/marlenech/BddPaye">Github</a>.

A très vite !
