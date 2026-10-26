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

Ce chapitre sera illustré par une image exemple.

Vous la trouverez [ici](https://github.com/NicOudart/UVSQ_EN3901_computer_vision/blob/master/images/Prairie_dog.jpg).

Il s'agit d'une photographie d'un _Cynomys ludovicianus_, aussi connu sous le nom de "Black-tailed Prairie Dog", prise en 2022 à Boulder (Colorado, USA).

![Image exemple du Chapitre 2](img/Chap2_example_image_black_tailed_prairie_dog.png)

N'hésitez pas à aller regarder les détails de la prise de vue de cette photographie dans les métadonnées !

## Le traitement d'image

## Transformations géométriques

### Agrandissement / rétrécissement

### Rotation / translation

![Exemples de translation et rotation d'image](img/Chap2_example_linear_filtering_kernel.png)

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

## Détection de forme

### La transformée de Hough

### Adaptation aux cercles

### Généralisation