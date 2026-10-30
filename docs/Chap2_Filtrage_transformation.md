# Chapitre II : Le traitement d'images, l'art du filtrage et de la transformation

Ce chapitre abordera les fondamentaux du traitement d'images numériques.
Il introduira entre autres les filtres et transformées qui sont à la base des outils "d'apprentissage profond" (ou "Deep Learning" en anglais) utilisés en "vision par ordinateur".

![En-tête chapitre II](img/Chap2_header.png)

_"Vibre la lumière, Chantez les couleurs, Il y met sa vie, Le bruit de son coeur._

_Et comme un bateau, Porté par sa voile, Doucement le pinceau, Glisse sur la toile._

_Et voilà l'homme, Qui croise avec ses yeux, Le temps d'un éclair, Le regard des dieux._

_Cézanne peint, Il laisse s'accomplir le prodige de ses mains._

_Cézanne peint, Et il éclaire le monde pour nos yeux qui n'voient rien."_

**Michel Berger & France Gall, Cézanne peint, 1985**

---

## Images exemples

Ce chapitre sera illustré par quelques images exemples.

Vous trouverez la première [ici](https://github.com/NicOudart/UVSQ_EN3901_computer_vision/blob/master/images/Prairie_dog.jpg).

Il s'agit d'une photographie d'un _Cynomys ludovicianus_, aussi connu sous le nom de "Black-tailed Prairie Dog", prise en 2022 à Boulder (Colorado, USA).

![Image exemple du Chapitre 2](img/Chap2_example_image_black_tailed_prairie_dog.png)

Par défaut, nous utiliserons cette image pour illustrer les différentes méthodes de traitement d'images.

Dans les cas spécifiques où nous avons besoin d'une image contenant des contours ou des coins bien définis, nous utiliserons une seconde image que vous trouverez [ici](https://github.com/NicOudart/UVSQ_EN3901_computer_vision/blob/master/images/Vizcacha.jpg).

Il s'agit d'une photographie d'une mosaïque représentant une _Lagidium peruanum_, aussi connue sous le nom de "Vizcacha del Norte", prise en 2025 à Huancayo (Pérou).

![Image exemple du Chapitre 2](img/Chap2_example_image_vizcacha.png)

Et dans les cas spécifiques où nous avons besoin d'une image avec des lignes ou des cercles à détecter, nous utiliserons une troisième image que vous trouverez [ici](https://github.com/NicOudart/UVSQ_EN3901_computer_vision/blob/master/images/Pika.jpg).

Il s'agit d'une photographie d'un _Ochotona princeps_, aussi connu sous le nom d' "American Pika", prise en 2022 au Rocky Mountain National Park (Colorado, USA).

![Image exemple du Chapitre 2](img/Chap2_example_image_pika.png)

N'hésitez pas à aller regarder les détails de la prise de vue des différentes photographies dans les métadonnées des images !

## Le traitement d'image

Lors du chapitre précédent, nous avons introduit le concept de "vision". 
Puis, nous avons parlé des problématiques liées à l'acquisition d'image avec une caméra.
Ensuite, nous avons parlé des problématiques liées à l'enregistrement d'images sous forme numérique.
Et enfin, nous avons introduit les concepts de "retouche" et "d'étalonnage" d'images.

La suite logique dans n'importe quel projet de vision par ordinateur est le **traitement d'image**.
Il s'agit de l'ensemble des **méthodes mathématiques** et **algorithmiques** "classiques" (hors IA) appliquables à des **images numériques** afin de les adapter à une méthode d'analyse, en faisant **ressortir des informations pertinentes**.

L'idée est qu'une image peut être considérée comme un signal discret 2D, et par conséquent on peut lui appliquer :

* Des manipulations **géométriques**, permettant d'adapter l'image selon un besoin spécifique en termes de dimensions, d'orientation, ou de translation spatiale.

* Des **filtres**, qui viennent modifier les valeurs des pixels de l'image pour faire **ressortir certaines propriétes spatiales** de l'image (les petits ou les gros élements, les contours, les coins, etc.).

* Des **transformations**, qui donnent accès à des **espaces de représentation différents** pour un image, permettant ainsi d'en tirer des **caractéristiques spatiales quantitatives** (fréquences horizontales ou verticales, lignes, cercles, etc.).

Ce chapitre vous présentera les outils de base en traitement d'image.
Il ne s'agira pas ici d'être exhaustif.
Nous nous attarderons en particulier sur les méthodes qui sont à l'origine de l'analyse d'images par IA, qui sera le sujet des 2 derniers chapitres de ce cours.

## Manipulations géométriques

Certaines applications de vision par ordinateur nécessitent d'adapter la dimension d'une image, de déplacer un objet sur une image, ou de changer son orientation.
Nous allons voir comment réaliser ces manipulations géométriques de base, et ce qu'elles impliquent en termes de reconstitution du signal contenu dans l'image.

### Agrandissement / réduction

Comme mentionné plus tôt, on peut considérer une image numérique comme un **signal 2D discret** noté $I[i,j]$ .
Par conséquent, modifier les dimensions d'une image numérique revient à **rééchantillonner** ce signal.

C'est ce que l'on appelle du "**redimensionnement d'image**".
Lorsque l'on cherche à augmenter les dimensions d'une image (et donc son nombre d'échantillons), on parle d'un "**agrandissement**".
Lorsque l'on cherche à diminuer les dimensions d'une image (et donc son nombre d'échantillons), on parle d'une "**réduction**".

La grande problématique du redimensionnement d'image est de respecter le **théorème de Nyquist-Shannon** vu au chapitre précédent : pour représenter discrètement un signal n'ayant pas de composantes fréquentielles supérieures à $f_{max}$, il faut choisir une fréquence d'échantillonnage $f_s$ telle que $f_s > 2 f_{max}$.

Une image étant un signal 2D discret, il faut donc que la fréquence d'échantillonnage respecte ce critère vis-à-vis de la plus grand fréquence spatiale contenue dans l'image, **selon les axes horizontaux et verticaux**.

Pour rappel, si ce critère n'est pas respecté lors du redimensionnement, l'image redimensionnée risque de souffrir d'un phénomène appelé **aliasing**, qui sera visible sous la forme d'artefacts appelé "Moiré".

![Exemples d'agrandissement avec différentes méthodes](img/Chap2_example_upscaling.png)

![Exemples de réduction avec différentes méthodes](img/Chap2_example_downscaling.png)

### Rotation / translation

![Exemples de translation et rotation d'image](img/Chap2_example_translation_rotation.png)

## Filtrage linéaire

### Convolution

### Choix du kernel

![Exemples de convolution d'une image par différents kernels](img/Chap2_example_linear_filtering_kernel.png)

## FFT et filtrage fréquentiel

### Analyse spectrale d'une image

![Exemple d'application de la FFT à une image](img/Chap2_example_image_FFT.png)

![Exemple d'application de la FFT à une image avec fenêtrage](img/Chap2_example_image_FFT_windowed.png)

![Exemple d'application de la FFT à une image avec des motifs périodiques](img/Chap2_example_image_FFT_cyclic_pattern.png)

### Filtrage en fréquences d'une image

![Exemple d'application d'un filtre passe-bas à une image](img/Chap2_example_lowpass_filtering.png)

![Exemple d'application d'un filtre passe-haut à une image](img/Chap2_example_highpass_filtering.png)

## Opérations morphologiques

### Element structurant

### Filtre médian

![Exemple d'application d'un filtre médian à une image bruitée "poivre et sel"](img/Chap2_example_median_filter.png)

### Erosion et dilatation

![Exemple d'érosion ou de dilatation d'image](img/Chap2_example_erosion_dilatation.png)

### Ouverture et fermeture

![Exemple d'ouverture et de fermeture d'image](img/Chap2_example_opening_closing.png)

## Détection de contours ou de coins

### Filtre de Sobel

![Exemple de filtrage de Sobel d'une image](img/Chap2_example_Sobel_filter.png)

### Filtre de Canny

![Exemple de filtrage de Canny d'une image](img/Chap2_example_Canny_filter.png)

### Filtre de Harris

![Exemple de filtrage de Harris et détection de coins d'une image](img/Chap2_example_Harris_filter.png)

## Détection de forme

### La transformée de Hough

![Exemple de détection de lignes par transformée de Hough](img/Chap2_example_hough_transform_lines_detection.png)

![Exemple d'accumulateur de transformée de Hough pour des lignes](img/Chap2_example_hough_transform_lines_detection_accumulator.png)

### Adaptation aux cercles

![Exemple de détection de cercles par transformée de Hough](img/Chap2_example_hough_transform_circles_detection.png)

![Exemple d'accumulateur de transformée de Hough pour des cercles](img/Chap2_example_hough_transform_circles_detection_accumulator.png)

### Généralisation