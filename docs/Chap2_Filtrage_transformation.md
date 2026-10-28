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

## Transformations géométriques

### Agrandissement / réduction

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