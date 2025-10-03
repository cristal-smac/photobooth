# bijective transformations of pictures

Cette page décrit la manière d'implémenter des transformations bijectives d'images.

En informatique, une image est constituée de points (pixels). c'est un
ensemble discret. Par exemple une image 100x100 contient 10000
pixels. C'est un ensemble fini, donc énumérable. On peut tous les
parcourir et leur appliquer des transformations (changements de couleurs par exemple). Un pixel est défini par ses
coordonnées dans un repère cartésien auquel est associé une couleur. 


Le principe de cette technique de transformation d'images consiste à
déplacer les points de l'image (en réalité les couleurs, car les
pixels proprement dits ne bougent pas) sans un perdre ni en ajouter :
c'est ce que l'on appelle communément un mélange. En mathématiques, un
mélange dans un ensemble fini correspond à ce que l'on appelle une
bijection (une application telle que tout élément de son ensemble
d'arrivée ait un et un seul antécédent).

On implémente donc des fonctions qui définissent ce mélange, donc qui à un
point de l'image fait correspondre un autre point.  D'où ce que les
auteurs ont appelé "Transformations bijectives d'Images" 

Parmi les plus connues :
- la translation à droite
- la transformation du photo-maton
- la transformation du boulanger


Parce que c'est une bijection, à force de l'appliquer, on retombe sur
la même image au bout d'un certain temps. C'est une propriété de
TOUTES les bijections dans un ensemble fini. 

La plus simple à comprendre est la translation à droite :
f(x,y) -> f(x+1 modulo taille , y) On comprend bien que au bout d'un nombre
d'étapes équivalent à la taille de l'image, tout sera revenu comme
initialement.

La plus spectaculaire : Le Photo-Maton
On prend chaque bloc de 4 pixels, et on fait en sorte que chacun de
ces 4 pixels s'en aille dans les 4 grandes parties de l'image.
Après une étape, on a l'impression d'avoir recopié 4 fois l'image en
petit, mais il n'en n'est rien ! C'est bien de 4 images différentes
qu'il s'agit. Elles se ressemblent mais elles sont différentes ! 

## Notebook
Français : [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/cristal-smac/photobooth.git/main?filepath=photobooth_fr.ipynb)


## Photo-maton Example
Tire son nom des célèbres cabines photo de l'entreprise Française [photomaton](https://fr.wikipedia.org/wiki/Photomaton) qui fournissaient 4 portaits en 2x2.

![alt text](pics/joconde_patchwork.png)

## Boulanger Example
Comme le fait le boulanger pour pétrir la pâte, à chaque étape on étire la pâte et on le replie sur elle-même.

![alt text](pics/chambord_patchwork.png)
