### 207 jours et 5h48 plus tard...

<img src = "https://media.giphy.com/media/LTYT5GTIiAMBa/giphy.gif"/>

Quoi ??? Deux mois se sont déjà écoulés depuis mon dernier article ???

Je vous vois déjà venir… « elle va encore nous sortir ses histoires de DSN, DADS, DUCS, et tous ses trucs bizarres qui lui prennent du temps au boulot, tu vas voir Georgette, c’est toujours les mêmes excuses ! ». Et bien non Georgette ! Figure toi que j’ai codé depuis tout ce temps, mais je le reconnais, pas vraiment sur le <span class="highlight-span">projet de CodingPaye</span>.

Comme je l’ai déjà évoqué sur ce blog, j’ai développé il y a quelques temps une application pour informer les bordelais des <span class="highlight-span">levées du Pont J. Chaban Delmas</span>. La saison des escales de paquebots débutant, il était nécessaire que je m’y consacre ces derniers temps afin d’optimiser l’appli, et apporter des nouveaux services aux utilisateurs. J’ai notamment effectué un important travail de refonte sur l’appli IOS. Et puis, poussée par une certaine inspiration, j’ai publié sur le même modèle une nouvelle application, cette fois pour informer des fermetures de l’ensemble <span class="highlight-span">des ponts de Bordeaux</span> (<a href="https://play.google.com/store/apps/details?id=com.italikdesign.ponts.bordeaux&hl=fr">Android</a> / <a href="https://itunes.apple.com/fr/app/les-ponts-de-bordeaux/id1219781460?mt=8">IOS</a>). Me voilà parée pour aborder cette nouvelle saison !

En ce qui concerne le projet CodingPaye, voici où j’en suis :

<img src = "https://marlenech.github.io/img/gif_03052017.gif"/>

Hormis le fait que les interfaces sont évidemment à retravailler,  j’ai réalisé mon premier <span class="highlight-span">calcul</span> sous Android ! Pour cela, il m’a fallu récupérer la donnée saisie par l’utilisateur dans l’EditText (= zone de saisie), la convertir en String (= chaîne de caractères) afin de me permettre de vérifier que l’EditText ne soit pas vide et contienne au moins un caractère et ainsi, lorsque la condition est remplie, convertir la chaîne dans un format me permettant d’intégrer la saisie dans un calcul (type float (ou double) = nombre décimal), puis lancer le calcul. 

<img src = "https://media.giphy.com/media/14syJ9o9fCpfby/giphy.gif"/>

Pour le moment, j’ai simplement appliqué au salaire brut un <span class="highlight-span">pourcentage de cotisations</span> afin d’obtenir un salaire net car évidemment, je suis loin d’avoir écrit l’ensemble des classes nécessaires à une conversion précise du salaire « Ok Georgette ! je n’ai pas commencé… ». Je vais m’attaquer alors à la partie la plus complexe de l’appli, mais aussi la plus importante : <span class="highlight-span">la formule de calcul de la conversion</span>.

Pour mener à bien cette mission, j’ai avant tout réfléchi à une architecture de l’application simplifiant toute modification. En effet, la technique de paie est loin d’être immuable. Ma base de données <a href="https://marlenech.github.io/2016/that's-done.html">gérée extérieurement à l’appli</a> me permet de mettre à jour les taux de cotisations sans intervenir dans le code de l’application, mais il est nécessaire également d’envisager des évolutions dans les formules de calcul applicables actuellement. Par exemple, l’assiette de cotisations de la CSG/CRDS est aujourd’hui composée de 0,9825 du salaire brut et de la part patronale des cotisations prévoyance, mutuelle, etc. Il se peut alors que cette contribution inclue à l’avenir d’autres cotisations ou que sa formule de calcul évolue. Il me faut alors pouvoir intervenir sur mon code sans nécessairement modifier l’ensemble de mes classes et interfaces.

<img src = "https://media.giphy.com/media/13mhYJQginrycU/giphy.gif"/>

Heureusement, il existe pour cela <span class="highlight-span">l’architecture MVC</span> (Model View Controller).
Initialement, lorsque l’on développe une application Android, le principe est de connecter chaque interface (vues de l’application) à une Activity (= classes qui vont déterminer les actions à appliquer pour chaque élément de l’interface). Ainsi, chaque interface est branchée à un modèle. L’interface affiche un bouton, et le modèle intègre le code évènementiel lors du clic sur ce bouton. Avec cette méthode, dès que l’interface change, le modèle est à changer, et vice versa.

Avec l’architecture MVC, le principe est d’ajouter dans notre arborescence <span class="highlight-span">un contrôleur</span>. Celui ci va alors servir de pont entre l’interface et le modèle et c’est lui qui va absorber les changements. Notre modèle gère les données de l’application, l’interface détermine la vue et enfin le contrôleur fait le lien entre l’interface et les données pour lancer les actions nécessaires au fonctionnement de l’application, modifier les vues si nécessaire, etc. Les modifications auront alors lieu dans le contrôleur et non pas dans le modèle et/ou l'interface.

Ainsi cette méthode va me permettre d’organiser mes calculs et intervenir rapidement, sans modifier profondément l’application lors de tout changement ou évolution.

Il ne me reste plus qu’à mettre ceci <span class="highlight-span">en pratique</span> !

<img src = "https://media.giphy.com/media/3oKIPx16LFvftHPLiM/giphy.gif"/>



A bientôt !



