# Segmentation-Champignons-INRAE

Ce git contient des implémentations de méthodes de segmentation d'images. Il s'agit de trouver les parties nécrosées de feuilles de colza dues à un champignon. Une fois trouvées, on peut décrire l'évolution de la maladie en fonction de sa variété et de la souche du champignon.

## Données

Les données sont des images de feuilles de colza. Un plan se voit inoculer une souche de champignon sur 2 de ses cotyledon. Ensuite, ces cotyledon sont pris en photo 7, 11 et 13 jours après l'inoculation.

**INSERER TABLEAU NBR PLANTS VARIETE/SOUCHE**

## Chaine de traitement

Chaque étape reçoit les images modifiées par l'étape précédente.

1. **Supprimer le fond des photos** pour ne garder **que la feuille**. *Segmentation des feuilles avec ImageJ*.

2. **Recaler les feuilles, (rotation, échelle, translation)** sur la première image chronologique. *Recalage en python avec une détection des contours et en utilisant la méthode de recalage Coherent Point Drift*.

3. **Segmentation des parties nécrosées** feuilles par feuilles.

4. Analyse statistique des plants et de leur maladie.

## Suppression du fond

Cette partie explique la suppression du fond pour ne garde que la feuille.

- ImageJ

## Recalage

Cette partie décrit comment le recalage s'effectue.

- Detection de bordure
- CPD

## Segmentation

On propose plusieur méthodes afin de détecter la partie malade du cotyledon.

- Seuillage :
  **>>>** 
  Histogram des couleurs de l'image.

- GMM :
  **>>>**

- Labelisation supervisée de pixels :
  **>>>** 
  1. À la main, segmenter l'image en trois catégories **background/feuille saine/feille malade**
  2. Utiliser une méthode supervisée pour classer les pixels : **NN/SVM/etc...**
  3. (éventuellement), utiliser les résultats des méthodes précédente pour labeliser, puis entrainer.
  
 ## Analyse statistique
 
Cette partie permettre de mettre en application la segmentation.
