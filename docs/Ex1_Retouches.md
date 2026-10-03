# Exercice 1 : retouche et étalonnage d'une image

## Sujet

Le but de cet exercice est de préparer une image pour une application de vision par ordinateur.
Vous la trouverez [ici](https://github.com/NicOudart/UVSQ_EN3901_computer_vision/blob/master/images/Ten_lined_june_beetle.jpg).

Il s'agit d'une image JPEG d'un _Polyphylla decemlineata_, une espèce de hanneton appelé "Ten lined June beetle" aux Etats-Unis :

![Image exemple de l'Exercice 1](img/Ex1_example_image_ten_lined_june_beetle.png)

Cette photographie a été prise dans le parc national "Great Sand Dunes" (Colorado, USA).
D'après ses métadonnées, elle a les propriétés suivantes :

|Propriété            |Valeur                    |
|:-------------------:|:------------------------:|
|Ouverture            |$f/2.8$                   |
|Temps d'exposition   |$1/2500 s$                |
|ISO                  |$80$                      |
|Distance focale      |$4 mm$                    |
|Résolution           |$3000 \times 3000$        |
|Poids                |$1.74 Mo$                 |
|Format               |JPEG                      |
|Profondeur de couleur|$24 bits$ (8 par primaire)|
|Encodage des couleurs|sRGB                      |

## Question 1

Pour prendre cette photographie, une caméra ayant un objectif classique constitué d'un lentille convergente, que nous considèrerons parfaite, a été utilisée.
Nous considèrerons que la lentille se trouve 

Imaginons que le hanneton se trouve à 25 cm de la caméra au moment de la photographie.

